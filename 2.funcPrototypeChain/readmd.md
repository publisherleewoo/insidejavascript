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