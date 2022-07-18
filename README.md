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

## oracle database를 이클립스에서 사용하기

이클립스의 data source explorer뷰를 선택하고 jdbc 드라이버 ojdbc6.jar를 jar list에서 설정해주고 db연결정보를 입력한다.

## 이클립스 웹 프로젝트 with SQL 생성하기

File -> New -> Dynamic Web Project 

WebContent 오른쪽 마우스 New -> Other -> SQL Development -> SQL File을 선택한다.

SQL FILE을 생성한다. File name : test.sql Database server type : Oracle_11 Connection Profile name Oracle11g Database name : xe

test.sql 파일에 SQL 구문을 입력할 수 있게 되었다.

## 이클립스에서 SQL 테이블 데이터 확인하기

test.sql 파일에 select * from EMPLOYEES 테이블명이 EMPLOYEES를 선택하는 SQL 구문을 입력하고 왼쪽마우스 Execute Selected Text를 선택하여 실행합니다.

Data Source Exploere -> Oracle11g -> xe -> Schemas -> HR -> Tables 를 보면 많은 테이블이 나오는데 그 중 EMPLOYEES를 선택하고 마우스 오른쪽 클릭 후 Data -> Edit을 누르면
해당 테이블의 데이터의 다양한 정보를 확인할 수 있습니다.  

## 표준 프레임워크 기반의 프로젝트를 생성하고 다양한 다이어그램의 사용법 익히기

표준프레임워크 기반의 프로젝트를 생성하기 위해서는 File -> New -> Other -> eGovFrame를 선택한 후 나오는 Wizard를 사용한다.

# 유스케이스 다이어그램 작성 방법
eGovFrame -> Analysis -> New Usecase Diagram 메뉴를 통해 유스케이스 다이어그램을 작성할 수 있다.

# 클래스 다이어그램 작성 방법
eGovFrame -> Design -> New Class Diagram 메뉴를 통해 클래스 다이어그램을 작성할 수 있다.

# ER 다이어그램 작성 방법
eGovFrame -> Design -> New ER Diagram 메뉴를 통해 ER 다이어그램을 작성할 수 있다.
