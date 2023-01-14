
## DBMS 개요와 MariaDB소개
### 개요
####    데이터
		* 현실 세계에서 측정하고 수집한 사실이나 값
		* 컴퓨터가 처리할 수 있는 문자, 숫자, 소리, 영상, 그림 등
####    테이터베이스
		* 데이터의 집합
		* 동시 접근 및 공유가 가능해야 함
####     DBMS(DataBase Management System)
		* 데이타베이스를 관리/운영하는 소프트웨어
		* MariaDB, MySQL, Oracle, SQL Server, DB2, PostgreSQL, SQLite, Access
####     Database 구성도
####     Database 특징
		* 무결성 --> 오류가 없는 정확한 데이터 확보
		* 중복 최소화 --> 동일한 데이터는 가능한 하나의 테이블에 저장
		* 독립성 --> 응용프로그램은 DBMS 변경에 영향받지 않아야 함
		* 보안성 --> 사용자별 데이터에 대한 접근 권한 관리
		* 안정성 --> 데이터 유실 및 하드웨어 문제 발생 시 복원 가능
####     관계형 Database
####    SQL
#####      정의
		 Database에서 사용되는 프로그램 언어
		표준 SQL : 국제 표준화 기관에서 작성한 표준화된 SQL
#####      특징
		- 독립성 : 표준 SQL은 DBMS와 상관없이 대부분 호환되나,각 DBMS 제품마다 특화 SQL을 추가하여 사용함
		- 표준 SQL의 지속적인 업그레이드 진행
		- 인터프리터형 언어 : 질의 -> 결과
## MariaDB소개
####    개요
####    변천사
# MariaDB 설치
## 설치
## Sample Databse 생성
## DBeaver 설치
MariaDB 전체 운영 실습
Database Modeling
MariaDB 유틸리티 사용법
### SQL 기본
#####     SQL분류
######       DML
			* Data Manipulation Language
			* 데이터 조작에 사용되는 언어
				- SLECT
				- INSERT
				- UPDATE
				- DELETE
* DML은 테이블을 대상으로 하며, 테이블이 정의되어 있어야 함
* 트랜젝션이 발생하는 SQL
--> DML 중 데이터 변경 SQL 문장 실행시 결과를 임시로 저장하여, 필요시 SQL 취소가 가능함(INSERT, UPDATE, DELETE)
######       DDL
#####     데이터 조회
#####      GROUP BY
#####      데이터 변경
#####      WITH절과 CTE
# SQL 고급
## DATA TYPE/ 형 변환
#####      숫자형
#####      문자형
#####      날짜/시간
#####      변수의 사용
#####      Data 형 변환
## 내장 / 윈도우 함수
#####      제어 흐름 함수
#####      문자열 함수
#####      수학 함수
#####      날짜 및 시간 함수
#####      시스템 정보 함수
#####      Text 데이터 대용량 입력하기
### JOIN
### SQL 프로그래밍
## 테이블과 뷰
## 인덱스
## 스토어드 프로그램
## 전체 텍스트 검색과 파티션
## 파이썬과 MariaDB 연동


