## CORS란?

- CROSS ORIGIN RESOURCE SHARING의 약자, 교차 출처 자원 공유라는 의미를 가지고 있다.

- ORIGIN: 1. SCHEME, 2. HOST, 3. PORT로 이루어진 도메인

EX)
https://www.naver.com/
이라는 도메인이 있으면,

1. scheme: https
2. host:www.naver.com
3. port:null(공개되지 않음)

- 현재 `자신이 속한 출처(origin)`를 기준으로 `다른 출처(origin)`에 API를 요청하게 되면 브라우저에서 `이 요청으로 넘어오는 경과가 안전한지 판단`하게 되는데, 응답을 보내는 출처가 다른 출처여도 서로 예상되는 출처라면 요청에 대해 허용해주는 응답 헤더를 보내서 응답 결과를 보여주게 된다.

### 실제 요청에서는 어떻게 처리하나

프론트 > WithCredentials: true

서버 > Access-Control-Allow-Credentials: true
