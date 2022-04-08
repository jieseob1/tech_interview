### INJECTION의 사전적 정의

주사,투입이라는 의미를 가지고 있다.

## SQL INJECTION

해커에 의해 조작된 SQL 쿼리문이 데이터베이스에 그대로 전달되어 비정상적 명령을 실행시키는 공격 기법

### 공격 방법

1. 인증 우회
2. 데이터 노출

### 방버 방법

1. INPUT 값을 받을 때, 특수문자 여부 검사
2. SQL 서버 오류 발생 시, 해당하는 에러 메시지 감추기
3. PREPARESTATEMENT 사용하기

https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer%20Science/Database/SQL%20Injection.md
