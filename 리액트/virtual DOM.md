## virtual DOM이란?

- DOM(Document Object Model:문서 객체 모델):`XML`이나 `HTML`문서에 `접근하기 위한` 일종의 인터페이스

- DOM은 문서의 구조화된 표현(STRUCTURED)을 제공
- 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공, 그들이 문서 구조, 스타일, 내용 등을 변경할 수 있게 돕는다.
  `HTTP response > DOM tree > CSSOM tree > render tree > painting`
- 리액트는 Virtual DOM을 사용하여 실제 DOM에 접근하여 조작하는 대신, 이를 추상화한 자바스크립트 객체를 구성하여 사용
  실제 DOM의 가벼운 사본과 비슷

- 실제 DOM을 업데이트 할 때는 다음 세가지 절차를 밟는다.

1. 전체 UI를 Virtual DOM에 리렌더링
2. 이전 부분과 현재 내용 비교
3. 바뀐 부분만 실제 DOM에 적용

### 결론

- 리액트와 Virtual DOM이 언제나 제공할 수 있는 것은 바로 `업데이트 처리 간결성` 이다.

1. UI를 업데이트하는 과정에서 생기는 `복잡함`을 모두 해소
2. 더욱 쉽게 업데이트에 접근
