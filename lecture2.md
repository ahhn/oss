# Week 2. AtoM 설치 및 실습
**May 20, 2017**
## 1. AtoM 설치
### 설치환경
OS : Ubuntu server 14.04 LTS

하드웨어 : 아마존 클라우드 서버 이용 - AWS EC2 1년 무료계정(Free tier)


### 설치
AtoM 설치 매뉴얼 : [https://github.com/ahhn/oss/blob/master/resources/AWS_v1.8.pdf](https://github.com/ahhn/oss/blob/master/resources/AWS_v1.8.pdf)



## 2. AtoM 실습
AtoM 튜토리얼 : [https://github.com/ahhn/oss/blob/master/resources/AtoM_tutorial_v1.1.pdf](https://github.com/ahhn/oss/blob/master/resources/AtoM_tutorial_v1.1.pdf)

### 기본 설정
- AtoM 인터페이스 둘러보기
- 한국어 추가
- 이용자와 그룹 만들기
- 메인페이지 소개글 작성

### 콘텐츠 등록
- 입수기록(Accession records) 등록
- 기록물 계층구조 정하기
- 기록물 등록 : ISAD(G)
- 입수기록과 연결하기
- 디지털 객체 업로드
- 전거레코드 등록 : ISAAR(CPF)
- 기록물소장기관 등록 : ISDIAH
- 보존서가 연결하기
- 분류체계 만들기
- 리포트 생성


# 코드 수정

<IfModule mod_fastcgi.c>

AddHandler php5-fcgi .php

Action php5-fcgi /php5-fcgi

Alias /php5-fcgi /usr/lib/cgi-bin/php5-fcgi

FastCgiExternalServer /usr/lib/cgi-bin/php5-fcgi -socket /var/run/php5-fpm.sock -pass-header Authorization <Directory /usr/lib/cgi-bin>

Require all granted </Directory>

</IfModule>
