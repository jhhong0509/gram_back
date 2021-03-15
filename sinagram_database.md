# 시나그램 데이터베이스 발표자료

<a href = "https://dog-developers.tistory.com/20">MySQL 설치 자료</a>

<a href="https://blog.naver.com/PostView.nhn?blogId=tipsware&logNo=221303732044&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=10&userTopListManageOpen=false&userTopListCurrentPage=1">MySQL workbench 설치 자료</a>

### 데이터베이스

통합하여 관리되는 데이터의 집합체

> 정말 쉽게 말하자면 실시간으로 변화하고, 여러 사람들이 동시에 접근할 수 있는 서버의 텍스트 파일

이러한 데이터베이스를 관리해 주는 프로그램을 데이터베이스 관리 시스템 이라고 한다.

### DBMS란?

데이터베이스의 관리를 도와주는 소프트웨어

데이터베이스의 구성, 접근방법, 유지관리에 대한 모든 책임을 진다.

> 프린세스 메이커

### DB의 종류

#### 계층형 데이터베이스

오래전에 사용되었던 형태

부모 - 자식 관계를 가짐

#### 관계형 데이터베이스

오랫동안, 많이 사용되고 있는 데이터베이스

대표적인 MySQL, ORACLE 등이 이에 속한다.

테이블로 구분되어 있으며, 각각의 데이터는 키를 통해 식별할 수 있다.

#### NoSQL

Not Only SQL의 약자

한가지 DB를 말하는게 아니다.

여러가지 종류의 DB들이 이에 속한다.

### SQL

- SQL이란?

  > SQL이란 Structed Query Language의 약자로, 단순 해석하면 구조화된 질문 언어 이다.
  >
  > Database에 질문 혹은 명령문을 내리는 언어를 말한다.

- SQL의 종류

  - DDL

    > DDL은 Data Definition Language의 약자로, 말 그대로 정의의 역할을 한다.
    >
    > 데이터베이스나 테이블 생성, 조작, 삭제등의 명령어를 말한다.

  - DML

    > DML은 Data Manipulation Language의 약자로, 데이터 조작 언어 라는 뜻 이다.
    >
    > 테이블이 아니라 하나의 데이터를 수정, 삭제, 삽입해 준다.

  - DCL

    > Data Control Language의 약자로, 객체들의 권한을 주고 회수해 준다.

  - TCL

    > Transaction Control Language의 약자로, 트랜젝션 제의어 이다.
    >
    > DML에 의해 작업된 결과를 작업단위(트랜잭션) 별로 제어해 준다.
    >
    > 쉽게 말해, 은행에서 돈을 보내는 것과 돈을 받는 것 둘중 하나라도 실패하면 둘 다 작동하지 않아야 하는 것

### MySQL

우리는 많은 데이터베이스중 MySQL을 이용하는 이유는 우선 오픈소스이기 때문에 무료이다.

또한 보안도 뛰어나며 속도도 빠르다. 게다가 모두 SQL을 기반으로 만들어졌기 때문에, 다른 데이터베이스를 사용할때도 별 차이 없다.

### MySQL workbench

MySQL workbench는 mysql을 쉽게 사용하기 위해 만들어진 GUI DBMS이다.

기본적으로 CLI 또한 사용할 수 있고, 쿼리의 재사용이 간편하며, GUI가 간편하다.

