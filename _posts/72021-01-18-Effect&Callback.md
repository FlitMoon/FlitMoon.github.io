---
layout: single
title: Effect & Callback
categories: React
tag: [react, coding, study, jsx, Effect, Callback, useEffect, useCallback]

toc: true
toc_sticky: true
toc_label: 목차
toc_icon: fas fa-utensils # font awesome

author_profile: false
---

# SideEffect
>앱이 제대로 동작하기 위해 실행되어야 하지만 현재의 컴포넌트 렌더링 과정에 직접적인 영향을 미치지 않는 작업

# useEffect

## 특징 1
```
useEffect(() => { 실행할 함수 }, [의존성] )
```
의존성으로 첨부한 값이 변할때만 해당 코드 실행됨.

## 특징 2
```
useEffect(() =>
	{
    	실행할 함수
        
        return () => {}
        
    }, [의존성]
)
```
effect함수가 다시 작동하기 바로 전이나 컴포넌트가 사라지기 바로 전에 실행
### 예시
```
const timer = setTimeout(() => { }, 3000);

    return () => {
      clearTimeout(timer);
    };
}, [ 의존성 ]);
```
타이머가 3초에 맞추어 실행되다가 `의존성`값이 변하거나, 모종의 이유로 해당 컴포넌트가 DOM에서 제거될때 (useState로 화면이 재로드 된다던지) `clearTimeout`이 실행되며 타이머가 제거된다.

# useCallback
> useCallback( 함수, 종속성array )

## 특징
> useCallback에 의해 실행된 함수는 의존성 값이 바뀌지않는 한 변경되지 않는다.

첫 실행시 함수를 저장한 후 해당 컴포넌트가 몇차례 다시 로딩 되더라도,
처음 저장한 함수를 불러온다는 의미.
