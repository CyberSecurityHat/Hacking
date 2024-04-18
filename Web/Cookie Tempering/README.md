# Cookie Tempering

### 취약점 설명

Cookie Tempering 즉, 쿠키 변조는 클라이언트 측에서 쿠키를 변조하는 공격입니다.
쿠키는 HTTP의 Connectionless를 해결할 뿐이며, 검증 등의 보안이 없기 때문에 안전을 보장하지 않는다.
그러므로 쿠키를 사용할 경우 신뢰할 만한 클라이언트인지 별도로 검증해야 한다.
만약, 그 검증이 미흡한 경우 공격자는 Cookie Tempering을 통해 해당 쿠키 사용자가 가진 권한을 얻을 수 있다.
