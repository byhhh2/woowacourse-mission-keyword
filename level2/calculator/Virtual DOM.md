## Virtual DOM이란?

- `ReactDOM`과 같은 라이브러리에 의해 `실제 DOM`과 `가상적인 표현`을 동기화
- VDOM은 `가상적인 표현`을 메모리에 저장하고 `실제 DOM`과 동기화하는 프로그래밍 개념 (= 재조정)
  - react의 선언적 API를 가능하게 한다.
  - react에게 원하는 UI의 상태를 알려주면 react가 DOM이 그 상태와 일치하도록 만들어준다.

### DOM이란?

- HTML과 JS를 이어주고, 작성한 HTML을 JS가 이해할 수 있도록 객체(노드)로 변환한다.
- 브라우저가 만든 트리구조 객체 모델

#### 브라우저의 동작원리 (렌더링이 일어나는 과정)

1. 브라우저가 HTML을 전달 받음
2. HTML을 파싱하여 노드로 이루어진 DOM 트리를 만듦
3. style을 파싱하여 스타일을 입힌 render 트리를 만듦
4. 레이아웃 배치
5. 변경 사항이 있을 시 DOM은 1~3 과정 반복

- 사소한 수정이 있을 경우에도 전과정을 다시 반복해야하므로 비효율적이다. -> Virtual DOM의 탄생
- 직접 DOM을 변경하는 일은 전체를 재렌더링하게 하기 때문에 브라우저에 과부하를 준다.

### Virtual DOM의 특징

- 일괄처리하는 전략
  - 리페인트가 발생하는 돔을 하나로 묶어 처리
  - 변경사항을 일괄 처리하고 한번에 DOM에 적용
- 수정사항이 여러가지가 있더라도, 한번만 렌더링을 일으킨다.
- 이전값과 현재값을 비교하여 달라진 부분만 DOM에게 전달하여 한번만 렌더링을 진행한다.
- Virtual DOM에 수정사항을 모으고, DOM과 Virtual DOM의 차이를 판단하고, 바뀐 부분만 찾아 변경한다.
- [Virtual DOM의 Three steps](https://doqtqu.tistory.com/316#toc-Virtual%20DOM%EC%9D%98%20Three%20Steps)

1. Virtual DOM을 수정한다.
2. Virtual DOM을 통해 DOM을 수정한다.

<br>
<br>

## 🤔 생각해보기

#### Reconciliation

- 수정사항이 있을 때 전후를 비교(diff)하여 갱신이 필요한 부분만 찾아 업데이트 하는 것

#### 우리는 JavaScript만으로 앱을 구성할 때 명령형으로 작성했을까요? 선언형으로 작성했을까요?

#### React 이전의 SPA 라이브러리들은 무엇이 있었을까요?

#### React 탄생 배경은 어떻게 될까요?

<br>
<br>

## 참고

- 우아한테크코스 LMS - Virtual DOM
- https://www.howdy-mj.me/dom/what-is-dom/
- https://dev-cini.tistory.com/10
- https://jeong-pro.tistory.com/210
- https://velog.io/@kim-jaemin420/reactVitual-Dom%EC%9D%B4%EB%9E%80-What-is-Virtual-Dom
- https://meetup.toast.com/posts/110

#### 공식문서

- [Virtual DOM](https://ko.reactjs.org/docs/faq-internals.html#what-is-the-virtual-dom)

<br>
<br>

## 더 공부할 키워드

- 리플로우, 리페인팅
- 명령형, 선언형
