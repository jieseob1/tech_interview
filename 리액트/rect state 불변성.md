## React에서 state의 불변성을 유지하라는 말이 있는데 이에 대해 설명해달라

- 객체는 실제 값이 아닌 참조값을 가진다.
- 복사하여 동일한 참조 값을 가지는 객체 중 하나만 변경되도, 모든 객체의 내부값이 변경된다.
- 스프레드 연산자를 통해 복사할 경우 a와 b는 같은 값을 가지더라도 새로운 객체를 할당 받은 상태가 된다.
  따라서 a,b의 내부의 값은 같아보여도, 참조하는 객체가 다르므로 무결성 유지 가능

## 리듀서 내부에서 불변성을 지키는 이유는? 스프레드 연산자의 단점 해결 방법

### 컴포넌트 업데이트 경우

- props가 바뀔때
- state가 바뀔 때
- 부모 컴포넌트가 리렌더링 될 때
- `this.forceUpdate`로 강제로 `렌더링을 트리거`할 때
  결국,렌더링 될때 임

- 불변성을 지킴으로써 각각의 고유한 참조값을 가지는 객체를 복사해서 사용함으로써 어떤 함수가 호출됐을 때 같은 객체를 참조한다면 생길 수 있는 불필요한 리렌더링과 부수효과를 줄일 수 있습니다.

- `...spread` 연산자를 사용하여 객체를 복사하게 되면, 객체의 깊이에 따라, 로직 구성이 어려울 수 있다.

const nextState = {
...state,
posts: state.posts.map((post) =>
post.id === 1
? {
...post,
comments: post.comments.concat({
id: 3,
text: "새로운 댓글",
}),
}
: post
),
};

이를 해결하기 위한 라이브러리가 `immer` 라이브러리이다.

`produce`, `draft`라는 키워드를 사용해서 기존의 `...spread`연산자를 사용하지 않고도 불변성을 유지해주며 불필요한 부수효과(side effect)를 막아준다.

const nextState = produce(state, (draft) => {
const post = draft.posts.find((post) => post.id === 1);
post.comments.push({
id: 3,
text: "와 정말 쉽다!",
});
});
