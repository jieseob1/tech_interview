## useMemo와 useCallback의 차이를 아나요

- useMemo: 메모이제이션된 값을 반환

- useCallback: 메모이제이션 된 함수를 반환

- 불필요한 리렌더링은 내가 만든 서비스의 성능 저하에 가장 큰 원인이 된다.

- 이렇게 특정 상황 (값, 또는 함수가 변경될 때)에 맞게 리렌더링이 될 수 있도록 useMemo와 useCallback 함수를 사용합니다.
