# Week 2. AtoM 설치 및 실습

**May 20, 2017**

## 1. AtoM 설치

### 설치환경
OS : Ubuntu server 14.04 LTS 
하드웨어 : 아마존 클라우드 서버 이용 - AWS EC2 1년 무료계정(Free tier)

### 1.1. Amazon EC2 접속 (via SSH)
-putty.exe를 실행하여 Amazon EC2 접속
-화면에 ubuntu 입력하여 로그인


### 1.2. root 계정 설정
-root 계정 비밀번호 설정
sudo passwd root

-새 비밀번호 입력(2회, 패스워드를 입력할 땐 화면에 패스워드가 출력되진 않지만 비밀번호가 입력된 것임)

-root계정으로 로그인(명령어 사이에 공백 유의)
su -

-기설정한 비밀번호 입력하여 로그인


### 1.3. Ubuntu 업데이트
-리눅스 Ubuntu 업데이트
sudo apt-get update

sudo apt-get upgrade

-Nano 에디터 설치
sudo apt-get install nano


### 1.4. 각종 어플리케이션 설치
-MySQL 설치
sudo apt-get install mysql-server-5.5

-Java 설치
sudo add-apt-repository ppa:webupd8team/java

sudo apt-get update

sudo apt-get install oracle-java8-installer

-ElasticSearch 설치
wget -qO - http://packages.elasticsearch.org/GPG-KEY-elasticsearch | sudo apt-key add -

nano /etc/apt/sources.list

deb http://packages.elasticsearch.org/elasticsearch/1.7/debian stable main


-업데이트 및 Elasticsearch 설치
sudo apt-get update

sudo apt-get install elasticsearch

-시스템 부팅 시 Elasticsearch 자동실행 설정
sudo update-rc.d elasticsearch defaults 95 10

sudo /etc/init.d/elasticsearch start


-웹서버 설치 (NGINX)
sudo apt-get install nginx

sudo add-apt-repository ppa:nginx/stable

sudo apt-get update

sudo apt-get install nginx


-기본서버 설정
sudo touch /etc/nginx/sites-available/atom

sudo ln -sf /etc/nginx/sites-available/atom /etc/nginx/sites-enabled/atom

sudo rm /etc/nginx/sites-enabled/default

sudo nano /etc/nginx/sites-enabled/atom

----------------------------------------------> 빈 화면이 나타나면 아래 upstream atom {부터


upstream atom {
  server unix:/var/run/php5-fpm.atom.sock;
}

server {

  listen 80;
  root /usr/share/nginx/atom;

  # http://wiki.nginx.org/HttpCoreModule#server_name
  # _ means catch any, but it's better if you replace this with your server
  # name, e.g. archives.foobar.com
  server_name _;

  client_max_body_size 72M;

  # http://wiki.nginx.org/HttpCoreModule#try_files
  location / {
    try_files $uri /index.php?$args;
  }

  location ~ /\. {
    deny all;
    return 404;
  }

  location ~* (\.yml|\.ini|\.tmpl)$ {
    deny all;
    return 404;
  }

  location ~* /(?:uploads|files)/.*\.php$ {
    deny all;
    return 404;
  }

  location ~* /uploads/r/(.*)/conf/ {

  }

  location ~* ^/uploads/r/(.*)$ {
    include /etc/nginx/fastcgi_params;
    set $index /index.php;
    fastcgi_param SCRIPT_FILENAME $document_root$index;
    fastcgi_param SCRIPT_NAME $index;
    fastcgi_pass atom;
  }

  location ~ ^/private/(.*)$ {
    internal;
    alias /usr/share/nginx/atom/$1;
  }

  location ~ ^/(index|qubit_dev)\.php(/|$) {
    include /etc/nginx/fastcgi_params;
    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
    fastcgi_split_path_info ^(.+\.php)(/.*)$;
    fastcgi_pass atom;
  }

  location ~* \.php$ {
    deny all;
    return 404;
  }

}

--------------------------------------------------------> } 까지 복사해서 입력

ctrl+O (저장)
ctrl+X (문서닫기)





-Nginx 재시작
sudo service nginx restart

-PHP 설치
sudo apt-get install php5-cli php5-fpm php5-curl php5-mysql php5-xsl php5-json php5-ldap php-apc

sudo apt-get install php5-readline


sudo nano /etc/php5/fpm/pool.d/atom.conf


-----------------------------------------------------> 빈 화면이 나타나면 [atom] 서부터
`
[atom]

# The user running the application
user = www-data
group = www-data

# Use UNIX sockets if Nginx and PHP-FPM are running in the same machine
listen = /var/run/php5-fpm.atom.sock
listen.owner = www-data
listen.group = www-data
listen.mode = 0600

# The following directives should be tweaked based in your hardware resources
pm = dynamic
pm.max_children = 30
pm.start_servers = 10
pm.min_spare_servers = 10
pm.max_spare_servers = 10
pm.max_requests = 200

chdir = /

# Some defaults for your PHP production environment
# A full list here: http://www.php.net/manual/en/ini.list.php
php_admin_value[expose_php] = off
php_admin_value[allow_url_fopen] = on
php_admin_value[memory_limit] = 512M
php_admin_value[max_execution_time] = 120
php_admin_value[post_max_size] = 72M
php_admin_value[upload_max_filesize] = 64M
php_admin_value[max_file_uploads] = 10
php_admin_value[cgi.fix_pathinfo] = 0
php_admin_value[display_errors] = off
php_admin_value[display_startup_errors] = off
php_admin_value[html_errors] = off
php_admin_value[session.use_only_cookies] = 0

# APC, which is still used in PHP 5.5 for userland memory cache unless you
# are switching to something like sfMemcacheCache
php_admin_value[apc.enabled] = 1
php_admin_value[apc.shm_size] = 64M
php_admin_value[apc.num_files_hint] = 5000
php_admin_value[apc.stat] = 0

# Zend OPcache
# Only in Ubuntu 14.04 (PHP 5.5).
# Don't use this in Ubuntu 12.04, it won't work.
php_admin_value[opcache.enable] = 1
php_admin_value[opcache.enable_cli] = 0
php_admin_value[opcache.memory_consumption] = 192
php_admin_value[opcache.interned_strings_buffer] = 16
php_admin_value[opcache.max_accelerated_files] = 4000
php_admin_value[opcache.validate_timestamps] = 0
php_admin_value[opcache.fast_shutdown] = 1

# This is a good place to define some environment variables, e.g. use
# ATOM_DEBUG_IP to define a list of IP addresses with full access to the
# debug frontend or ATOM_READ_ONLY if you want AtoM to prevent
# authenticated users
env[ATOM_DEBUG_IP] = "10.10.10.10,127.0.0.1"
env[ATOM_READ_ONLY] = "off"

`

ctrl+O (저장)
ctrl+X (문서닫기)




-프로세스 관리자 재시작
sudo service php5-fpm restart

-PHP 실행 테스트
sudo php5-fpm --test

-Gearman 잡서버 설치
sudo apt-get install gearman-job-server

-Apache FOP 설치 (아래 내용을 반드시 1줄씩 입력하세요)
sudo -s

wget https://archive.apache.org/dist/xmlgraphics/fop/binaries/fop-2.1-bin.tar.gz

tar -zxvf fop-2.1-bin.tar.gz

rm fop-2.1-bin.tar.gz

mv fop-2.1 /usr/share

ln -s /usr/share/fop-2.1/fop /usr/bin/fop

echo 'FOP_HOME="/usr/share/fop-2.1"' >> /etc/environment

exit


-ImageMagick 설치
sudo apt-get install imagemagick ghostscript poppler-utils

-ffmpeg 설치
sudo add-apt-repository ppa:archivematica/externals

sudo apt-get update

sudo apt-get install ffmpeg


### 1.5. AtoM 설치
-AtoM 2.2.1 다운로드
wget https://storage.accesstomemory.org/releases/atom-2.2.1.tar.gz

sudo mkdir /usr/share/nginx/atom

sudo tar xzf atom-2.2.1.tar.gz -C /usr/share/nginx/atom --strip 1


### 1.6. 파일시스템 접근권한 설정
sudo chown -R www-data:www-data /usr/share/nginx/atom

sudo chmod o= /usr/share/nginx/atom


### 1.7. 데이터베이스 생성
mysql -h localhost -u root -p -e "CREATE DATABASE atom CHARACTER SET utf8 COLLATE utf8_unicode_ci;"

mysql -h localhost -u root -p -e "GRANT INDEX, CREATE, SELECT, INSERT, UPDATE, DELETE, ALTER, LOCK TABLES ON atom.* TO 'atom'@'localhost' IDENTIFIED BY '12345';"












### 
### 
### 
### 
### 
### 
### 
### 

## 2. AtoM 실습
