<h1> 1주차 - 리액트 개념</h1>
<h2> 리액트 기초 개념</h2>
오픈소스 자바스크립트 라이브러리로 프론트 엔드 웹 개발을 위해서 사용된다
컴포넌트라는 코드의 조각을 이용하여 UI를 구성한다
<h2>리액트 특징</h2>
1. virtualDOM을 사용해서 수정사항이 발생하면 최소한의 부분만 재 렌더링을 해서 빠른 업데이트와 렌더링이 가능하다
<br>
2. 여러개의 컴포넌트를 기반으로 하는 구조이기때문에 코드 재사용이 용이하다
<br>
3. props를 사용해서 부모 컴포넌트로부터 자식 컴포넌트로 데이터를 전달 할 수 있다
<br>
4. state를 사용해서 동적으로 변하는 데이터를 다룰 수 있다
<h3>리액트 컴포넌트</h3>

```
const h1 React.createElement('h1', null,'Hello World);
```
위와 같이 리액트 라이브러리를 이용해서 간단한 컴포넌트를 만들 수 있다

함수형 컴포넌트는
```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
위 코드 처럼 함수의 형태를 가지는 함수형 컴포넌트를 제작가능하다<br>
함수형 컴포넌트는 매개변수로 받은 데이터를 컴포넌트에 반영 가능하다는 장점이 있다

아래 코드로 클래스의 형태를 가지는 클래스 컴포넌트 또한 제작 가능하다

```javascript
class Welcome extends React.Component<props> {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

이렇게 만들어진 리액트 컴포넌트가 물리 DOM트리 멤버객체가 되어 처음 렌더링이 일어나는 것을 컴포넌트 마운트라고 한다

<h3>props</h3>
자식 컴포넌트에 데이터를 전달하는 것을 목적으로 한다

```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
이렇게 전달받은 props의 하위 속성인 name에 접근 가능하다

key 속성은 각 컴포넌트마다 적용 가능하고 같은 이름이 여러개인 컴포넌트를 구별하기 위한 속성이다 <br>
이 속성이 없다면 console에서 에러 메시지를 출력하지만 웹페이지 동작에는 문제가 없다

children 속성은 자식 컴포넌트를 가질 수 있는 컴포넌트만 사용 가능한 속성이다


<h3>이벤트</h3>
화면 Ui에서 발생한 사건을 이벤트라고 한다

<h4>이벤트 속성</h4>
- type : 이벤트 이름<br>
- isTrusted : 이벤트가 브라우저에서 발생했으면 true, 프로그래밍에 의한 것이면 false 반환<br>
- target : 이벤트가 처음 발생한 html 요소<br>
- currentTarget : 이벤트의 현재 대상. 버블링 도중에 이벤트가 위치한 객체<br>
- bubbles : 이벤트가 버블링 될지 여부<br>

자식요소에서 발생한 이벤트가 부모 요소까지 차례로 전달되는 것을 이벤트 버블링 이라고 한다
<br>가장 먼 부모 요소까지 모두 이벤트가 전달된다

<h4>이벤트 핸들러</h4>
이벤트를 기다리는 콜백 함수이다<br>
그중에서 eventlistner는 이벤트 발생을 감지하는 역할을 한다
<br> 이외에도 addEventListner, removeEventListner 등의 메서드가 있다

```javascript
const rootDiv = document.getElementById('root')
if(rootDiv){
	rootDiv.onClick = (e:Event) => console.log('clicked')
}
```

stopPropagation 메소드를 이용하면 버블링을 중지 시킬 수 있고 그렇게 버블링을 중지하는 것을 event capturing이라고 한다
