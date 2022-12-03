# Generics_TS
### Before Learning Generics 
타입스크립트의 중요 문법 중 하나인 Generics 에 대해서 다루는 리포입니다.  [TypeScript Generics](https://reinvented-specialist-02e.notion.site/Prototype-Generic-a6d4b5ee8010465b93fb876d9550f38a) 


### #Generic이란 (제네릭)

---

- **사용 목적** : **재사용성이 높은** 컴포넌트를 만들때 활용합니다. 즉 **여러가지 타입**에서 동작하는 컴포넌트를 생성할때 유용

### #Generic을 왜 사용할까요?

---

🤔 사용 목적만 봤을때는 그래서 제네릭이 왜 필요한지 확 와닿지가 않습니다. 

그래서 제네릭을 활용 안했을때의 단점에 대해서 설명코자 합니다.

### 1. 기존 타입정의 방식 vs 제네릭

함수 중복 선언으로 인한 유지보수성의 저하 

⇒ **같은 기능**을 하는 함수를 정의하고 싶을때, 받을 수 있는 param의 type의 한계점을 꼽을 수 있습니다. 

즉 기존 타입 정의 방식으로 정의한다면, 함수에 선언된 내용(기능)은 같지만 **Param의 type으로 인해** 함수를 중복 선언하게 됩니다. 

 ****

### 2. 유니온 타입을 이용한 선언 방식의 문제점

1. type을 여러개 받을 수는 있지만, **교집합**의 성질을 지니고 있기 때문에,
한정된 method (string과 number 2개의 type을 모두 지원하는 메소드만) 를 지원받게 됩니다.
2. 함수를 호출한 매개변수 역시 type의 대한 정의가 모호해짐

![union의 문제점.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/343f0ac4-c652-454b-b6f7-df6ec1adbfc9/union%EC%9D%98_%EB%AC%B8%EC%A0%9C%EC%A0%90.png)

`a` 라는 변수에 hover 시, type으로 string | number 로 나옵니다. 그렇기 때문에 `split()` 이라는 string type을 지원하는 메소드를 인식하지 못하게 됩니다.