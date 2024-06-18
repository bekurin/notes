### 생성 날짜: 2024-01-12T23:37
### 주제: OAuth 1.0
---
### 본문:
소셜 로그인 기능으로 잘 알려진 OAuth는 서드파티 서비스가 인증을 제공해주는 것을 넘어. "사용자의 인증 정보를 제공하지 않고, 서비스 인증이 가능하게 할 수 있을까?"라는 고민에서 고안된 방법입니다.

사용자의 인증 정보를 제공하지 않아도 인증이 된다는 것은 사용자가 서비스를 이용하기 위해 온갖 곳을 돌아다니면서 회원가입을 할 필요가 없다는 것을 뜻합니다.

### OAuth 1.0의 주요 컴포넌트

- 소비자(Consumer): 서드파티 서비스를 통해 인증을 받고 싶은 클라이언트
- 서비스 제공자(Service Provider): oauth1.0 스펙을 지원하는 서버
- 사용자(User): 자원 소유자 (본인)
- 소비자 키와 비밀(Consumer Key and Secret): 클라이언트 자격 증명
- 요청 토큰과 비밀(Request Token and Secret): 임시 자격 증명
- 접근 토큰과 비밀(Access Token and Secret): 토큰 자격 증명

![[oahth1.0.drawio.png]]
위 그림을 따라가면서 구조를 알아보겠습니다.
- user: 홍길동
- service: 페이스북 글 목록 확인
- facebook: OAuth 1.0을 지원하는 서비스 제공자

홍길동은 여러 소셜 미디어에 업로드한 글 목록을 볼 수 있는 service를 사용하고 싶지만 해당 service에 회원가입을 하거나 인증 정보를 넘겨주고 싶지는 않습니다.

이런 경우를 대비해 service는 임시 자격 증명, resource owner 인증, 토큰 요청 URL을 미리 생성했습니다.
- 임시 자격 증명: https://service.net/temporary
- resource owner 인증: https://service.net/authorize
- 토큰 요청 API: https://service.net/token

홍길동은 글 목록 접근 권한을 요청하기에 앞서 service에서 임시 자격 증명을 획득해야합니다. 예시 http 요청은 아래와 같습니다.

```
POST /initiate HTTP/1.1
Host: photos.example.net
Authorization: OAuth realm="",
	oauth_consumer_key="",
    oauth_signature_method="",
    oauth_timestamp="",
    oauth_nonce="",
    oauth_callback="http%3A%2F%2Fservice.net%2Fready-for-temporary-authorize",
    oauth_signature=""
```

oauth 1.0은 유효 시간이 긴 인증 토큰 사용과 웹 환경에서 사용해야한다는 한계점이 있습니다. OAuth 2.0은 이러한 한계를 극복했습니다.

OAuth 2.0, 2.1에 대해서도 알아보겠습니다.

---
### 참고문헌
- 
---
### 연결문서
- 

