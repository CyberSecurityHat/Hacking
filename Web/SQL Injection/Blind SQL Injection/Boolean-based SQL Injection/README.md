# Boolean-based Blind SQL Injection

### 취약점 설명

이 취약점은 Blind SQL Injection의 일종으로, True와 False의 반환값의 차이를 통해서 DB 데이터를 알아낸다.<br>
Blind SQL Injection이기 때문에 반환값에 DB 쿼리 결과 데이터가 반환되지 않는다.<br>
그러나 True와 False 반환을 구분할 수 있기 때문에 SQL 쿼리를 이용하여 데이터를 알아낼 수 있다.<br>
이 취약점은 SQL Injection이 가능하고, 반환값의 차이를 통해서 True와 False를 구분할 수 있을 때 사용할 수 있다.
