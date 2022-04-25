## Props란?

> `state` : 변경할 수 있는 상태  
> `props` : 변경할 수 없는 상태, 읽기 전용으로 전달받는 데이터 (불변 데이터)

- react component에 전달되는 데이터로 부모 컴포넌트나, `defaultProps`를 통해 전달된다. (주로 부모)

### Props가 불변 데이터여야 하는 이유는?

- `setState()`가 state를 곧바로 갱신하는게 아니라, 상태 전환을 `pending`하기 때문!
- `setState()` 이후, 직접 `this.state`에 접근하게 되면 갱신되지 않은 상태일 수 있다. => 이는 디버깅에 어려움을 줄 수 있기 때문에 불변 데이터로 다뤄야 한다.

### Props Drilling

- 오로지 하위 컴포넌트로 전달하기 위해 컴포넌트를 거쳐 다른 부분으로 데이터를 전달하는 과정 => 유지보수가 진심 어려움 (겪어봄)
- Props를 수정할 수 없기 때문에 여러 차례 Props를 넘기게 된다.
- 이로 인해 깊어지는 component depth와 무분별하게 전달되는 props의 문제가 발생
- 해결법 : 전역 상태관리 라이브러리 사용 등

<br>
<br>

## 🤔 생각해보기

#### 리액트에서 속성을 불변 객체로 다루는 이유는 무엇일까요? 또, 불변 객체로 다루지 않았을 때 발생할 수 있는 이슈는 무엇일까요?

- state가 갱신되기 전에 state에 접근할 경우 문제가 될 수 있다.

#### 하위 컴포넌트에서 상위 컴포넌트의 상태인 Props 를 직접 수정할 수 없는 이유는 무엇일까요?

#### Prop Drilling을 해결할 수 있는 방법은 Context API 혹은 Redux 같은 State Container와 Store Management뿐일까요?

<br>
<br>

## 참고

- 우아한테크코스 LMS - Props
- https://slog.website/post/13
