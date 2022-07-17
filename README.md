# SpringFramework
Spring Framework studying 표준전자정부 프레임워크


## 개발자 통합 개발 환경 설치

https://www.egovframe.go.kr/home/ntt/nttRead.do?pagerOffset=0&searchKey=&searchValue=&menuNo=65&bbsId=4&nttId=1741 에서 개발자 통합 개발 환경 설치 한다.
eclipse, 톰캣, mysql, jdk, android-sdk 등이 포함되어 있다.

## 서버 개발 환경 구축

VisualSVN Sever를 http://subversion.apache.org/packages.html 에서 설치해준다. 이때 port는 8443으로 변경한다.

## 오라클 설치 및 설정

오라클 설치를 하기 전 eclipse-servers에서 tomcat v8.0 sever를 우클릭 후 start 실행해줘서 8080포트를 선점해줘야 오라클 설치 과정에서 http port를 8081로 변경하는 창이 나온다.
https://www.oracle.com/database/technologies/xe-prior-release-downloads.html oracle 11g XE는 여기서 다운로드한다.

오라클이 기본적으로 제공하는 hr 유저와 테이블을 사용하기 위해서는 잠금 해제를 해야 한다.

관리자(dba) 권한을 가진 sys유저와 패스워드를 입력하여 접속한다.
```
connect sys/manager as sysdba
```

hr 유저의 계정의 암호를 hr로 설정하고 계정의 잠금을 해제한다.
```
alter user hr identified by hr account unlock;
```

hr 유저로 접속한다.
```
connect hr/hr
```

기본적으로 제공되는 테이블의 이름을 확인한다.
```
select tname from tab;
```
