## 함수의 정의
+ 함수 선언문 (function statement)
+ 함수 표현식 (function expression)
+ Function() 생성자 함수

```javascript
//함수 리터럴을 통한 add함수 정의,  함수 선언문
function add(x,y){
    return x+y;
}

//함수를 변수에 표현. 변수에 할당.  변수에 할당했으므로 식, 함수 표현식
var min = function (x,y){
    return x-y
}

```

```javascript

//함수변수들은 동일한 익명함수를 참조한다.        
var add = function (x,y){
return x+y
}
var plus = add;
console.log(add(3,4));
console.log(plus(5,6));
```


## 자바스크립트에서 함수가 일급객체인 이유
+ 리터럴에 의해 생성
+ 변수나 배열의 요소,객체의 프로퍼티 등에 할당 가능
+ 함수의 인자로 전달 가능
+ 함수의 리턴값으로 리턴 가능
+ 동적으로 프로퍼티를 생성 및 할당 가능

```
위키백과중...
컴퓨터 프로그래밍 언어 디자인에서, 일급 객체(영어: first-class object)란 다른 객체들에 일반적으로 적용 가능한 연산을 모두 지원하는 객체를 가리킨다. 보통 함수에 매개변수로 넘기기, 수정하기, 변수에 대입하기와 같은 연산을 지원할 때 일급 객체라고 한다.
```


## 함수는 값이며 객체(!)다
```javascript
var bar = function(){
	return 100;
};
bar();
var obj = {};
obj.baz = function(){return 200};
obj.baz();

```

+ 함수의 매개변수로 활용
  
```javascript
var foo = function(func){
    func();
}

foo(function(){
    console.log("인자로넘긴코드!")
})

```
+ 함수의 리턴값으로 활용

```javascript
var foo = function(){
	return function(){
		console.log("이것은 함수의 리턴값함수")
	}
}
var bar = foo()
bar()
```


## ECMA5 명세서
+ 모든 함수는 length,prototype프로퍼티를 가져야한다.
+ name 프로퍼티는 함수의 이름
+ caller프로퍼티는 자신을 호출한 함수


## 자바스크립트 객체는 [[Prototype]] 내부 프로퍼티를 가진다.
+ 크롬브라우저에서는 __proto__ 프로퍼티로 구현되어있다.
+ 함수 역시 자바스크립트 객체이므로 __proto__ 프로퍼티를 가지고있다.
+ 함수 객체의 부모 역할을 하는 프로토타입 객체를 Function.prototype 객체 라고 명명하고있으며 함수객체라고하고 
  + constructor 프로퍼티
  + toString 메서드
  + apply(thisArg,ArgArray) 메서드
  + call(thisArg,[,arg1[,arg2,]]) 메서드
  + bind(thisArg,[,arg1[,arg2,]]) 메서드


## 함수명.length
  + 함수 인자의 개수
  
## prototype 프로퍼티
  + 모든 함수는 객체로서 prototype 프로퍼티를 가지고있다. 명세프로퍼티인 [[prototype]]과 다르다.
  + prototype과 constructor 프로퍼티는 서로를 참조하게된다.


## 스코프체이닝으로 인해 내부함수는 자신을 둘러싼 외부함수의 변수에 접근이 가능하다, 반면에 함수 내부에 선언된 변수는 함수 외부에서 접근이 불가능 하다
```javascript
function parent(){
    var a = 100;
    var b = 200;
    function child(){
        var b = 300;
        console.log(a)
        console.log(b)
    }
    child()
}
parent()

```


## 함수 스코프 외부에서 내부함수를 호출하는 예제코드
```javascript
    function parent(){
        var a = 100;
        var child = function(){
            console.log(a)
        }

        return child
    }

    var inner = parent();
    inner()

```