# XSS (Cross Site Scripting)

### 공격 설명

XSS는 웹페이지에 악성 스크립트를 삽입하는 공격이다.

#### XSS 종류

- Reflected XSS (Non-persistent XSS) - 서버에 악성 스크립트를 요청하여 결과페이지에 실행되어 출력 됨.<br>
- Stored XSS (Persistent XSS) - 악성 스크립트를 서버에 저장하여, 서비스를 제공하는 정상페이지에서 지속적으로 다른 사용자들에게 스크립트가 노출되어 악성 스크립트가 실행 됨.<br>
- DOM Based XSS - Javascript 코드로 DOM 객체를 제어하여 악성 스크립트를 실행함. 브라우저 상에서 이루어짐.
