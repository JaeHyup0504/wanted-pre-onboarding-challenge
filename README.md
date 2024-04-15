# 원티드 프리온보딩 프론트엔드 챌린지 사전과제

### 1. Virtual DOM의 개념과 동작 방식에 대해 설명해주세요.
1. Virtual DOM이란?

    DOM의 추상화된 개념으로, 실제 DOM(Document Object Model)을 조작하는 방식이 아닌, 실제 DOM을 모방한 가상의 DOM을 구성해 원래 DOM과 비교하여 달라진 부분을 리렌더링 하는 방식으로 작동합니다.

3. Virtual DOM의 동작 방식
    1. UI가 변경을 감지하면 UI를 Virtual DOM으로 렌더링합니다. (실제 화면상 렌더링 되는 것이 아닌 비교를 위한 가상 렌더링)
    3. 현재 Virtual DOM과 이전 Virtual DOM을 비교해 차이를 계산합니다.
    4. 변경된 부분을 실제 DOM에 반영합니다.

### 2. React Hooks은 무엇이며 어떻게 사용되나요? 
1. useState, useEffect 등 React Hooks에 대해 간략히 소개해주세요.
    
    React 16.8 버전에서 도입된 기능으로, 함수형 컴포넌트에서도 상태 관리와 라이프사이클 기능을 사용할 수 있게 해주는 API입니다. 
Hook을 사용하면 이전에는 클래스형 컴포넌트에서만 가능했던 상태 관리와 라이프사이클 메소드를 함수형 컴포넌트에서도 사용할 수 있으며 코드의 재사용성과 가독성을 높일 수 있습니다. useState, useEffect, useContext, useReducer, useCallback, useMemo 등이 있습니다.
    
2. 클래스 컴포넌트와 함수형 컴포넌트의 차이점에 대해 설명해보세요. 

   **문법과 구조**
    - 클래스형 컴포넌트 : ES6의 클래스 문법을 사용하며 React.Component를 상속받아 구현합니다.
    - 함수형 컴포넌트 : 일반 함수로 작성되며, 별도의 클래스 상속 없이 구현 코드의 간결합니다.

   **코드 가독성**
    - 클래스형 컴포넌트 : 코드가 상대적으로 길고 복잡하여 가독성이 떨어집니다.
    - 함수형 컴포넌트 : 코드가 간결하여 가독성이 높습니다.

   **상태 관리**
    - 클래스형 컴포넌트 : this.state와 this.setState를 사용하여 상태를 관리합니다.
     - 함수형 컴포넌트 : useState Hook을 사용하여 상태를 관리합니다.
     
   **라이프사이클 메서드**
    - 클래스형 컴포넌트 : 라이프사이클 메서드를 사용하여 컴포넌트의 생성, 업데이트, 제거에 대한 로직을 구현합니다.
    - 함수형 컴포넌트 : useEffect Hook을 사용하여 라이프사이클 메서드와 유사한 기능을 구현합니다.


### 3. React Router의 주요 기능과 사용법에 대해 설명해주세요.
1. React Router란? 

   클라이언트 측 라우팅(URL의 여러 경로로 서로 다른 페이지를 로드할 수 있는 기능)을 구현하는 데 사용되는 라이브러리입니다.
SPA에서 페이지 간의 전환 및 URL 경로와 컴포넌트 간의 매핑을 관리하는 데 도움이 됩니다.

 2. React Router 주요 기능 및 사용법
    
    **BrowserRouter** - 경로를 인식하기 위한 태그입니다.
    **Routes** - Route들을 포함하며 Route들은 반드시 이 태그 안에 포함되어야 정상 작동합니다.
    **Route** - URL을 통해 컴포넌트 경로를 지정합니다.
    **Link** - 라우터 내에서 직접적으로 페이지 이동을 하고자 할 때 사용합니다.
 ```js
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/detail" element={<Detail />} />
      </Routes>
    </Router>
  );
}
export default App;
 ```
```js
import React from 'react';
import { Link } from 'react-router-dom';

function Nav(){
  return (
    <div>
      <Link to='/'> Home </Link>
      <Link to='/detail'> Detail </Link>
    </div>
  );
}
export default Nav;
```

### 4. 아래는 상품의 가격이 담긴 객체 배열입니다. 

```js
 const products = [
    {id: 1, product: 'Laptop', price: 7200},
    {id: 2, product: 'Headphones', price: 6000},
    {id: 3, product: 'Mouse', price: 2000},
    {id: 4, product: 'keyboard', price: 4200},
    {id: 5, product: 'desktop', price: 10800},
];
```
1. price가 높은 순으로 정렬된 List를 반환하는 함수를 작성해주세요.
```js
const sortProducts = products.sort((a, b) => b.price - a.price)
```

2. price가 6000 이상인 제품들의 인덱스를 찾아, 해당 제품들의 이름을 배열로 반환하는 함수를 작성해주세요.
```js
const filterProducts = products.filter((product) => product.price > 6000).map((product) => product.product)
```


