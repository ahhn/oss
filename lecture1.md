# Week 1. OSS & AWS & GitHub

**May 13, 2017**


## 1. 오픈소스 소프트웨어 개요

오픈소스 소프트웨어 개념과 구축사례
- [1/3](https://github.com/ahhn/oss/blob/master/resources/OSS1.pdf)
- [2/3](https://github.com/ahhn/oss/blob/master/resources/OSS2.pdf)
- [3/3](https://github.com/ahhn/oss/blob/master/resources/OSS3.pdf)

오픈소스 소프트웨어 라이선스
- [Open Source Initiative 인증 라이선스 목록](https://opensource.org/licenses)

인공지능 오픈소스 써 보기
- [Google Cloud Natural Language API](https://cloud.google.com/natural-language/)
- [IBM Watson Natural Language Understanding](https://natural-language-understanding-demo.mybluemix.net/)
- [IBM Watson Vision Recognition](https://visual-recognition-demo.mybluemix.net/)


## 2. AWS를 이용한 클라우드 서버 구축 

- [AWS 사이트](https://aws.amazon.com)

- 회원가입 (신용카드를 등록해야 합니다)
- 주의 : AWS EC2는 1년 무료(Free Tier)로 사용할 수 있지만 계정당 1개의 서버 인스턴스만 쓸 수 있습니다(월 720시간). 만약 하나의 계정으로 2개 이상의 서버 인스턴스를 사용하게 되면 사용량만큼 요금이 청구됩니다. 1년 후 부터는 매월 요금이 청구되니 그 전에 인스턴스 상태(State)를 사용안함(Stop) 또는 종료(Terminate)시켜야 합니다.

- AWS EC2 우분투 서버 인스턴스 만들기

- Key file(.pem) 저장하기 > 이메일로 보내기(필수!)

- [Putty 다운로드 사이트](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)

- Puttygen.exe 다운로드

- Putty.exe 다운로드

- Puttygen.exe 실행하여 Key file(.pem)을 다른 형식(.ppk)으로 변환하여 저장하기

- Putty.exe 실행하여 .ppk 파일 등록하고 AWS EC2 URL(Public IP) 등록하기

- Putty를 이용하여 AWS EC2 서버에 접속 (via SSH)

- [Linux 명령어 실습](http://nuninaya.tistory.com/158)


### Youtube 영상
- [AWS EC2 계정 만들기](https://www.youtube.com/watch?v=sQSQCqihygc&list=PLya-3fVEf50Zj0bfFbkRpxuwO6J9mh4Pf&index=5)
- [AWS EC2 우분투 서버 설치하고 세팅하기](https://www.youtube.com/watch?v=DcnQeLfg7gM&list=PLya-3fVEf50Zj0bfFbkRpxuwO6J9mh4Pf&index=4)
- [AWS EC2 우분투 서버 루트관리자 계정 만들기](https://www.youtube.com/watch?v=qhAM79x0SvQ&index=3&list=PLya-3fVEf50Zj0bfFbkRpxuwO6J9mh4Pf)
- [APM 구동원리, 설치 및 환경설정하기](https://www.youtube.com/watch?v=r5Fy8N3-WDs&index=2&list=PLya-3fVEf50Zj0bfFbkRpxuwO6J9mh4Pf)
- [AtoM 설치하기](https://www.youtube.com/watch?v=eaw7rN_O6LM&list=PLya-3fVEf50Zj0bfFbkRpxuwO6J9mh4Pf&index=6)
- [Omeka 설치하기](https://www.youtube.com/watch?v=4HUJtZNPtlQ&index=1&list=PLya-3fVEf50Zj0bfFbkRpxuwO6J9mh4Pf)


### 매뉴얼

- [AtoM 설치](https://github.com/ahhn/AtoM_UserManual_kor/blob/master/AtoM%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC(%E1%84%8B%E1%85%A1%E1%84%8F%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%87%E1%85%B3%E1%84%85%E1%85%A2%E1%86%B8-%E1%84%8B%E1%85%A9%E1%84%91%E1%85%B3%E1%86%AB%E1%84%89%E1%85%A9%E1%84%89%E1%85%B3%E1%84%8B%E1%85%A7%E1%86%AB%E1%84%80%E1%85%AE-20170430)(%E1%84%87%E1%85%A2%E1%84%91%E1%85%A9%E1%84%8B%E1%85%AD%E1%86%BC)(mpm-event%E1%84%8B%E1%85%AA%20php5-fpm%E1%84%87%E1%85%A5%E1%84%8C%E1%85%A7%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC).pdf)
- [Omeka 설치](http://osasf.net/uploads/FileUpload/dc/35fc351c736a808dde5c9bff895dd8.pdf)
- [AWS EC2 웹서버에 아카이브 만들기](https://github.com/ahhn/oss/blob/master/resources/AWS_v1.7.pdf)



## 3. GitHub 

오픈소스 리포지터리 만들기

- GitHub 소개 [영문](https://guides.github.com/activities/hello-world/), [한글1](http://icoder.tistory.com/entry/GitHub-Guides-Hello-World), [한글2](http://guruble.com/?p=116)

- [GitHub 사이트](https://github.com/)

- 회원가입

- 로그인

- 리포지터리 만들기

- OSS 라이선스 선택하기

- README.md 파일 수정하기


오픈소스 프로젝트 찾기

- 오픈소스 프로젝트 찾아보기

- 오픈소스 프로젝트 라이선스, 개발언어, 인기도 확인하기

소스코드 변경하기

- 소스코드 가져오기(Fork)

- 소스코드 수정하기

- 소스코드 커밋(Commit)하기

- 오픈소스 프로젝트에 반영 요청하기(Pull request)

오픈소스 프로젝트 설명하기

- 폴더 만들고 Info.md 파일 만들기

- 폴더에 파일 업로드

- [GitHub 페이지 만들기](https://pages.github.com/)

- [GitHub Wiki 만들기](https://help.github.com/articles/about-github-wikis/#)

- GitHub 실습 - md파일 만들기


## 4. 과제 안내

- AtoM과 Omeka 중 하나를 선택하여 설치하고 기록물 등록/기술하기

- GitHub 리포지터리에 AtoM과 Omeka의 소개 또는 이용방법을 작성하고 오픈소스 라이선스로 공개하기

- 6/3(토) 과제 작성결과 발표하기

<br/><br/>
### Markdown 소개 (OOO.md 파일)

Markdown 은 깃허브에서 문서(OOO.md)를 작성할 때 쉽게 사용할 수 있는 문법입니다. 아래의 규칙을 익혀 보세요.

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

더 많은 정보를  보시려면 [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).




## 참고 링크
###OSS 프로젝트###
- ICA-AtoM - [https://www.ica-atom.org/](https://www.ica-atom.org/)
- AtoM - [http://accesstomemory.org](http://accesstomemory.org)
- Omeka - [http://omeka.org](http://omeka.org)
- Omeka.net - [http://omeka.net](http://omeka.net)
- Omeka S - [http://omeka.org/s](http://omeka.org/s) 
- Omeka Everywhere - [https://github.com/ideum/omeka-everywhere/](https://github.com/ideum/omeka-everywhere/)
- Curatescape - [https://curatescape.org/](https://curatescape.org/)
- ArchivesSpace - [http://www.archivesspace.org/](http://www.archivesspace.org/)
- Collective Access - [http://www.collectiveaccess.org/](http://www.collectiveaccess.org/)
- Archivematica - [https://www.archivematica.org](https://www.archivematica.org)
- Binder - [https://binder.readthedocs.io/en/latest/contents.html](https://binder.readthedocs.io/en/latest/contents.html)
- DPSP (Digital Preservation Software Platform) - [http://dpsp.sourceforge.net/](http://dpsp.sourceforge.net/)

###AtoM 구축사례###
- [AtoM 구축사례 목록](https://wiki.ica-atom.org/ICA-AtoM_users)
- [UNESCO Archives AtoM Catalogue](https://atom.archives.unesco.org/)
- [World Bank Group Archives Holdings](https://archivesholdings.worldbank.org/)
- [JMABC (Jewish Museum & Archives of BC)](https://archives.jewishmuseum.ca/)
- [City of Vancouver Archives](http://searcharchives.vancouver.ca/)
- [MemoryBC](https://www.memorybc.ca/)
- [Archeion](https://www.archeion.ca/)
- [인간과기억아카이브](http://hmarchives.org/)
- 국립문화재연구소 연구관리시스템

###Omeka 구축사례###

**국내**
- [부산대학교 로컬리티아카이브](http://localityarchives.org/)
- [한국여성의전화 여성인권운동아카이브 문](http://herstory.xyz/)
- [김세진이재호기억저장소](http://snu.osasf.net/)
- [성공회대학교 대한마이크로노동조합 아카이브](http://micro.osasf.net/)
- [세월호인양의 모든것](http://time.416family.org/)
- [인간과기억아카이브](http://hmarchives.org/omeka/exhibits)
- 서울시 북부교육청 교육역사전시관
- 기획재정부 연혁정보관리시스템
- 인천대학교 인천학연구원 아카이브
- 광명시 평생학습아카이브
- 동물보호시민단체 카라(진행중)
- 공주학연구원(진행중)

**해외**
- [Omeka 구축사례 목록](https://omeka.org/codex/Sites_Using_Omeka)
- [Occupy Archive](http://occupyarchive.org/)
- [Our Marathon](http://marathon.neu.edu/)
- [Bracero History Archives](http://braceroarchive.org/)
- [Documenting FERGUSON](http://braceroarchive.org/)
- [Baltimore Uprising 2015](http://baltimoreuprising2015.org/)
- [Wearing Gay History](Wearing Gay History)
- [MORE](http://moremuseum.org/omeka/)
- [Human Computers at NASA](http://omeka.macalester.edu/humancomputerproject/)
- [DPLA](http://dp.la)
- [Histories of the National Mall](http://mallhistory.org/)
- [Cleveland Voices](https://clevelandvoices.org/)

###Curatescape 구축사례###
- [Curatescape 구축사례 목록](https://curatescape.org/projects/)
- [Cleveland Historical](https://clevelandhistorical.org/)
- [동대문구 기억여행](http://dgo.osasf.net/)


###오픈소스 커뮤니티###
- [AtoM User's Group]()
- [Omeka Forum]()
- [Archivematica User Forum](https://groups.google.com/forum/?fromgroups#!forum/archivematica)
- [Curatescape Forum]()
- [기록관리 공개소프트웨어 포럼](http://osasf.net](http://osasf.net)



