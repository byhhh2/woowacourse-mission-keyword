## JSX란?

JavaScript를 확장한 문법으로 자바스크립트 코드 안에서 HTML 문법을 사용할 수 있음

- react element를 생성한다.
- react는 렌더링 로직이 UI 로직과 느슨하게 연결 (컴포넌트로)
  - 분리하는 것은 인위적이다!

### JSX의 특징

- JSX의 중괄호(`{}`) 안에는 유효한 모든 JavaScript 표현식을 넣을 수 있다.
- JSX의 속성에는 따옴표(`""`) 또는 중괄호(`{}`)가 들어갈 수 있다.
  - JSX는 HTML보다는 JS에 가깝기 때문에 속성이름에 camelCase를 사용
- babel은 JSX를 `React.createElement()`호출로 컴파일한다.

```js
const element = <h1 className="greeting">Hello, world!</h1>; // 1

const element = React.createElement(
  'h1',
  { className: 'greeting' },
  'Hello, world!'
); // 2

// 1 === 2

const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!',
  },
};
// React.createElement()가 생성한 객체
// 이 객체는 react element라고 한다.
// React는 이 객체를 읽어서, DOM을 구성하고 최신 상태로 유지하는 데 사용합니다.
```

<br>
<br>

## 🤔 생각해보기

```js
import React from 'react';
import ReactDOM from 'react-dom'; // 2

const element = <h1>Hello, world!</h1>;

ReactDOM.render(element, document.getElementById('root')); // 1
```

#### `#root`를 미리 선언해놓는 이유는 무엇일까요? [1]

- root DOM 노드
  - root DOM 노드에 들어가는 모든 엘리먼트를 React DOM에서 관리
- react element를 root DOM 노드에 렌더링하려면, react element와 root DOM 노드를 `ReactDOM.render()`로 전달하면 된다.

#### React는 들어본 것 같은데 react-dom은 무엇일까요? [2]

- React DOM이란 Virtual DOM에서 HTML을 생성하는 데 필요한 라이브러리이다.
- React DOM은 React 엘리먼트와 일치하도록 DOM을 업데이트한다.

#### render가 하는 일은 무엇일까요? [1]

- [`ReactDOM.render()`](https://ko.reactjs.org/docs/react-dom.html#render)

```js
ReactDOM.render(element, container[, callback])
// element를 container DOM에 렌더링한다.
```

---

```js
import React from 'react';
import ReactDOM from 'react-dom';

const element = React.createElement('h1', 'Hello, world!');

ReactDOM.render(element, document.getElementById('root'));
```

#### JSX와 표현식은 같을까요? && JSX와 React.createElement() 는 무슨 관계일까요?

```js
const element = <h1>Hello, world!</h1>; // JSX
const element = React.createElement('h1', 'Hello, world!'); // 표현식
```

- babel이 JSX를 `React.createElement()`호출로 컴파일한다. - [참고](https://ko.reactjs.org/docs/introducing-jsx.html#jsx-represents-objects)

#### document.createElement()와 다른 점은 무엇일까요?

- `document.createElement()` : return DOM element
- `React.createElement()` : return object (= react element)
- [참고](https://ko.reactjs.org/docs/introducing-jsx.html#jsx-represents-objects)

<br>
<br>

## 참고

- https://withseungryu.tistory.com/57

### 공식 문서

- [JSX 소개](https://ko.reactjs.org/docs/introducing-jsx.html)
- [react-dom](https://ko.reactjs.org/docs/react-dom.html)

<br>
<br>

## 더 공부할 키워드

- react-dom 라이브러리
- virtual DOM
