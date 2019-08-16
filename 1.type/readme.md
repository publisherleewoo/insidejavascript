## 자바스크립트의 데이터 타입

+ 기본타입(호출방식: 값에 의한 호출 : call by value, 복사)
    + 숫자
    + 문자
    + 문자열
    + 불린값
    + undefined
    + null

+ 참조타입(호출방식: 값에 의한 호출 : call by reference,참조)
    + 객체
        + 배열
        + 함수
        + 정규표현식


## 메서드
+ 함수로 표현된 프로퍼티는 메서드라고한다.


## 자바스크립트에서 객체를 생성하는 방법
+ Object() 객체 생성자 함수를 이용하는 방법
+ 객체 리터럴을 이용하는방법
+ 생성자 함수를 이용하는 방법


## 자바스크립트 명세서
+ 명세서에는 [[Prototype]]
+ 브라우저에서는 __proto__


## Array
+ length 프로퍼티는 가장 큰 인덱스값의 +1
+ typeof []  === object  자바스크립트는 배열도 객체
+ splice(start,deleteCount,item)   item은 삭제할 위치에 추가할 요소이다.
+ 자바스크립트에서 일반 객체에 length라는 프로퍼티가 있으면 유사배열객체라고 부른다.
```javascript
    var arr = ['bar'];
    var obj ={
        name:'foo',
        length:1
    }
    arr.push('baz');
    console.log(arr)
    obj.push('baz')  //error
```
+ apply,call메서드를 사용하면 객체지만 표준 배열 메서드를 활용하는것이 가능하다.
+ arguments 객체가 아래같이 사용가능
```javascript
    var arr = ['bar'];
    var obj = {name:'foo',length:1};

    arr.push('baz');
    console.log(arr)

    Array.prototype.push.apply(obj,['baz'])
    console.log(obj)
```

## 기본타입 표준 메서드
+ wrapper, boxing
+ 기본타입일때는 스택, 메서드를 붙이면 힙구조로 래퍼객체화

## typeof 연산자
+ null,배열,객체  === object
+ 함수는 function
+ undefined 는 undefined


```javascript
console.log(1 == "1") //true
console.log(1 === "1") //false
``` 

## !!연산자
+ !!의 역할은 피연산자를 불린값으로 변환
```javascript
console.log(!!0); //false
console.log(!!1); //true
console.log(!!"string"); //true
console.log(!!""); //false
console.log(!!true); //true
console.log(!!false); //false
console.log(!!null); //false
console.log(!!undefined); //false
console.log(!!{}); //true
console.log(!![1,2,3]); //true
```