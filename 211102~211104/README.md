# 211102~211104 TIL

## EC2

> **mysql 서버 설치 및 연동**
>

- [MySQL ERROR 1698 (28000): 에러 해결](https://www.lesstif.com/dbms/mysql-error-1698-28000-89555999.html)
- [[AWS] EC2에 MySQL 서버 구축하기](https://velog.io/@issac/AWS-EC2%EC%97%90-MySQL-%EC%84%9C%EB%B2%84-%EA%B5%AC%EC%B6%95%ED%95%98%EA%B8%B0)

## FastAPI(Backend)

> **bcrypt, jwt를 통한 암호화/복호화**
>

- [[암호화] bcrypt로 암호화 시작하기](https://velog.io/@anrun/%EC%95%94%ED%98%B8%ED%99%94-bcrypt%EB%A1%9C-%EC%95%94%ED%98%B8%ED%99%94-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0)

> **SQLAlchemy를 통한 DB 연결**
>

- [SQL (Relational) Databases - FastAPI](https://fastapi.tiangolo.com/tutorial/sql-databases/)
- [FastAPI(2): MySQL CRUD](https://velog.io/@wmc1415/FastAPI2-MySQL-CRUD)

> **Backend 우선순위 제작**
>

- ~~**회원가입**~~
- 게시판
- 메인 페이지

> **nginx location 변경으로 인한 에러**
>

![107543941-fd778880-6bc9-11eb-9e4c-3b8686db0528](https://user-images.githubusercontent.com/50372451/140331949-38e8d50c-2eda-4bb6-9280-0017f1569d43.png)

해결 : [https://github.com/tiangolo/fastapi/issues/2787](https://github.com/tiangolo/fastapi/issues/2787)

> **nginx 설정하기**
>

## test token

**`eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1aWQiOjEsInVzZXJfaWQiOiJtZWFudGludCIsInVzZXJfbmFtZSI6Im1vayIsInBob25lX251bWJlciI6IjAxMDUzNjYxMjM0In0.Ty-t3GtdYgm76kSUbmperUzJflRJBRlICkE8laaqWSc`**

## pip install

- fastapi
- uvicorn
- pymysql
- sqlalchemy
- pyjwt
- bcrypt

## 느낀 점

1. Jenkins를 통한 자동 배포를 프론트엔드 브랜치 설정을 통해 배웠다. 백엔드 브랜치 설정은 배운 것을 토대로 해서 주말에 직접 해볼 예정이다.

2. 이번주가 프로젝트 외적으로 꽤 바빠서 시간에 쫓기면서 백엔드 API 제작을 혼자했고 DB Table 구축과 Jenkins, Docker 사용을 도움을 받고 공부하면서 제작을 했는데 단기간에 많이 배운 것 같아서 보람찼다.

3. nginx 너무 어렵다...
