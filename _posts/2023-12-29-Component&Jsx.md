---
layout: single
title: 리액트 Component와 Jsx
categories: React
tag: [react, coding, study, component, jsx]

toc: true
toc_sticky: true
toc_label: 목차
toc_icon: fas fa-utensils # font awesome

author_profile: false
---

# 컴포넌트
![](https://github.com/FlitMoon/FlitMoon.github.io/assets/154722228/fc28b964-d6f4-4a05-bfb7-4a87e1896b76)

## 정의

<ul>
  <li>잠재적으로 재사용이 가능한 구성 요소.</li>
  <li>리액트 개발자가 직접 제작하고 차후 혼합하여 하나의 UI를 제작해낼 수 있다.</li>
</ul>

※ 관례적으로 파일이름과 컴포넌트명은 동일하게 작성한다.

### 구성
<font color='#d05252'>컴포넌트 트리</font>

![Component Tree](https://github.com/FlitMoon/FlitMoon.github.io/assets/154722228/6f561261-cbd6-4258-8b38-5fd713ada276)
부모 컴포넌트( App )와 그 아래 자식 컴포넌트들의 계층구조가 설립된다.

## 특징

<ul>
  <li>코드의 재사용이 가능하기 때문에, 반복되는 코드의 수정이 한번에 가능하다.</li>
  <li>비슷한 코드는 함께 저장 된다.</li>
  <font color='red'>ㄴ</font> 한가지 기능에 관련된 코드들이 한곳으로 모인다는 뜻.
  <li>각각의 컴포넌트는 다른 기능을 가지며, 필요한 UI를 구성하는데 유리하다.</li>
  <li>Jsx라는 문법을 사용한다.</li>
</ul>

### JSX
>JSX = JavaScript Syntax Extension

개발자가 자바스크립트 파일 내에 HTML마크업 코드를 작성하여 HTML요소를 설명, 생성할 수 있게 함.

## 컴포넌트의 조건 & 형태
### 조건
<ul>
  <li>함수에서 렌더링이 가능한 값이 반환 되어야 한다.</li>
  <li>함수의 제목은 대문자로 시작.</li>
  <li>여러줄의 코드 반환시 return()로 감쌀 것.</li>
</ul>

### 예시코드
```
function Header() {
    return (
        <header>
            <h1>Hello!</h1>
            <p>이것은 예시코드 입니다.</p>
        </header>
    );
}

export default Header;
```
※	다른 파일에서 사용하기 위해 export를 해주며,<br/>
사용할때에는 import후에 사용하면 된다.

## 사용 형태

>커스텀 컴포넌트의 경우 JSX코드 내에서 HTML요소 처럼 사용된다.

### 예시코드
```
import Header from ' Header예시코드의 경로 ';

export default () => {
	return (
    	<Header></Header>  or  <Header />
        
        <h1>Hello~</h1>
    )
}
```

