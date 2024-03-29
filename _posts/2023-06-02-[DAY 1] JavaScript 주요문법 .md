## 변수, 상수, 자료형 그리고 메모리

### 변수

~~var~~ → ES6 자바스크립트 버전이 나오기 전 사용했음 ( 호이스팅이라는 자바스크립트라는 특이한 동작 때문에 권장하지 않음)

let → ES6 이후로 사용가능, 변수 선언시 권장

예 ) let variable = 126;

variable = 메모리 상 주소 = 서울시 마포구 마포대로 122

126 =  주소에 해당하는 값 = (37.5453577, 126.9503578)

집은 언제든지 허물어 새로운 건물을 세울수 있는 것처럼, 메모리상 값도 언제든지 바꿀수있음.

### 상수

- 변하지 않는 값.

const 

예 ) 법적으로 건물을 허물 수 없도록 특별히 막음. but 패킹등을 통해 해당 메모리 값을 변경할수는 있음

### 자료형

- Number : 숫자, 실수까지 모두 다 , Nan, infinity
- String : 문자열 ( “”, ‘’, 백틱, \(이스케이프문자 앞에 붙이기) )
- Boolean : true, false
- Object : 여러 자료형을 키를 통해 가질 수 있는 타임. 키는 무조건 문자열
- Array : 키를 갖고있지 않으며, index 를 통해 값을 찾을 수 있음
- Function : 함수
- Undefined :  변수 혹은 상수가 선언되었지만 아무런 값도 대입되지 않음
- Null : 해당 변수가 비어있음을 사용자가 의도적으로 나타날때 사용

### 메모리

할당 → 사용 → 해제

javascript 는 Garbage Collector 로 메모리가 꽉차면 메모리를 해제함
<br>

## 메모리 심화

javascript 는 원시타입은 변경이 불가능

원시타입의 값이 변경될때는 항상 새로운 메모리가 할당됨

Call Stack : 원시타입

Heap : 참조타입 (배열=object타입)

메모리가 지워지는 건 참조가 중요함. 
<br>

## 표현식과 연산자

일반적으로 웹사이트는 여러개의 자바스크립트로 이루어져 있다.

대부분 스크립트 언어의 특징이지만, 자바스크립트는 파일들을 각각 별개의 프로그램으로 취급합니다.

자바스크립트는 프로그램은 무엇으로 이루어져있을까요?

표현식, 문장 두가지 문법적 카테고리로 이루어져있다고 볼수있다

> 표현식이란..?
> 

어떠한 결과 값으로 평가되는 식이다.

숫자, 문자열, 논리값 같은 원시 값을 표현하여 변수 상수, 함수 호출 등으로 조합할 수 있다.

> 연산자
> 

- 할당 연산자

    오른쪽 표현식을 왼쪽 피연산자 값에 할당하는 연산자 등호(=) 를 사용하며 다른 연산자와 같이 사용하여 복합 연산자로 이용할 수 있다.

- 비교 연산자

    좌측 피연산자와 우측 피연산자를 비교하는 연산자. true or false 반환

- 산술 연산자

    덧셈,뺄셈,곱셈,나눗셈을 하는 연산자. number 를 반환

- 비트 연산자

    비트를 직접 조작하는 연산자

- 논리 연산자

    boolean 을 통해 참과 거짓을 검증. 조건문이나 반복문에서 자주사용

- 삼항 연산자

    조건에 따라 값을 선택하는 연산자 ` 조건 ?  참 : 거짓 ` 형태를 가짐

- 관계 연산자

    객체에 속성이 있는지 확인하기 위한 연산자

```css
const x = {
	name : "bang ji-hyun",
	email : "wlgysdl3@naver.com",
};

"name" in x; // true
"gender" in x; // false
```

- type of
    
    피연산자의 타입을 반환하는 연산자. 문자열로 반환됨
    <br>
    <br>
    

## 흐름제어 문법

### control flow

흐름을 제어하는 방법 중 하나로 조건이나 반복을 통해 상태를 제어

- 조건문 (if, else if, else, switch (case,default) )
    
    조건이 맞을 때만 실행되는 문장
    
    false 뿐만 아닌 다음 값들도 거짓이 될 수 있으니 주의 해야한다.
    
    false, undefined, null, 0, NaN, “(empty string)
    
- 반복문 (for, while, do-while)
    
    반복적인 작업을 지시하는 문법
    
    while :  괄호안 조건이 거짓이 될 때까지 반복한다
    
    do-while : while문과 다르게 먼저 진입 후, 로직을 실행한 다음 조건을 검사한다.
    
<br>
<br>
## 배열과 객체

### 배열

연관된 데이터를 연속적인 형태로 저장하는 복합타입 배열에 포함된 원소는 순서대로 번호(index) 가 붙는다.

## Javascript 에서 배열 사용법

### 배열 생성 방법

`Source`

```jsx
// 빈 Array를 생성할 수 있습니다.
const arr1 = new Array () ;

const arr2 = [ ];

// 미리 초기화된 Array를 생성할 수 있습니다.
let arr2 = [1, 2, 3, 4, 5];

// 많은 값을 같은 값으로 초기화할 경우 을 쓸 수 있습니다.
let arr3 = Array(5).fill(0);

// 특정 로직을 사용하여 초기화할 경우 from을 사용할 수 있습니다.
let arr4 = Array. from({ length: 100 ), (_. i) => i);
```

`Output`

```
[]
[]
[1, 2, 3, 4, 5]
[0, 0, 0, 0, 0]
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99]
```

### 배열 요소 추가 & 삭제

```jsx
const arr = [1, 2, 3];

// 4가 끝에 추가됩니다.
arr.push(4); 

// 여러 개를 한 번에 추가할 수 있습니다.
arr.push(5, 6); 
console.log(arr);
//[1,2,3,4,5,6]

// 3번 인덱스에 128을 추가합니다.
arr.splice(3, 0, 128); 
console.log(arr);
//[1,2,3,128,4,5,6]

//3번 인덱스 값을 제거합니다.
arr.splice(3, 1);
console.log(arr [3]);
// [4]
```

## 특이점

자바스크립트의 배열은 인덱스가 숫자가 아닌 문자열이나, 논리값도 들어갈 수 있다. 이는 자바스크립트의 배열이 근본적으로 객체타입이기 때문이다. **인덱스와 무관한 값을 인덱스로 사용한 경우 길이에 영향을 미치지 않는다.** 

이러한 코드는 좋은 코드는 아니다. 이러한 특징이 있다는 것만 알아두고 넘어가자

```jsx
const arr = [1,1,2,3]

console.log(arr,length)
// 4

arr["string"] = 10;
arr[false] = 0;
console.log(arr) 
// [1,1,2,3, string:10 , false:0]
console.log(arr.length)
// 4

arr [4] = 5
console.log(arr.length)
// 5

const arr = [1,2,3,4,5]
arr.length = 3
console.log(arr);  // [1,2,3]

const arr1 = new Array();  // [ ]

const arr2 = [ ];  // [ ] 

const arr3 = [1,2,3,4,5] // [1,2,3,4,5]

const arr4 = new Array(5);  // [<5 empty items>]

const arr5 = new Array(5),fill(5);  // [5,5,5,5,5]

const arr6 = Array.from(Array(5), function (v,k) {
	return k+1;
});
console.log(arr6)  // [1,2,3,4,5]
 v = 배열의값, k = 배열의 인덱스
```

## 배열 Method

```jsx
// join

console.log(arr.join(",")); //1,2,3,4,5

// reverse → *****reverse 함수는 한번 변경되면 원래 함수에도 영향을 미치므로 주의해서 사용해야한다.*****

console.log(arr.reverse());  // [5,4,3,2,1]

// concat

const arr1=[1,2,3,4,5,6];

const arr2=[7,8,9,10];

console.log(arr1.concat(arr2));  // [1,2,3,4,5,6,7,8,9,10]

// pop, push, shift, unshift → 뒤에 원소 삭제, 추가 / 앞에 원소 삭제, 추가

// slice ***→ 배열 중간의 잘라서 값을 알고싶다 **-> *** slice 는 원본배열이 변화하지는 않는다.**
const arr = [1,2,3,4,5,6];

consle.log(arr.slice(2,4) // [3,4] *→ index 2번째부터 ~ 4번째 앞 원소까지 잘라낸다.*

// splice → 중간의 배열을 삭제하고 싶다

const arr = [1,2,3,4,5,6];

console.log(arr.splice(2,2) // [1,2,5,6] *→ 2번 index 부터 2개를 삭제한다.*

```

## 배열 (for 문 /  for of 문)

```jsx
const arr = [1,2,3,4,5,6];

for ( var i =0 ; i < 6;  i += 1) {
	console.log(arr(i);
}

// 1,2,3,4,5,6

for (const item of arr) {
	console.log(item);
}

// 1,2,3,4,5,6
```
<br>
# 객체

## 객체 생성

```jsx
const obj1 = new Object( );  // { }

const obj2 = { };  // { }

const obj = { name: "amy" , age: "29"};
```

```jsx
// 객체 추가
obj["email"] = "wlgysdl3@naver.com"
[obj.phone](http://obj.phone) = “01000000000”

// 객체 내 정보 삭제 
delete obj.phone;

// in operator 를 이용하여 key 가 있는지 확인하기.
console.log("email" in obj);   // true
console.log("phone" in obj);  // false

// 객체 내 key 와 value 집합 구하기
console.log(Object.keys(obj) // [”name”, “age”, “email”] → 배열의 형태로 key 나옴 
console.log(Object.values(obj) // [”amy”, “29”, “wlgysdl3@naver.com”] → 배열의 형태로 value 나옴
```

## for in 문

```jsx
const obj = { name: "amy" , age: "29"};  

for ( const key in obj) {

console.log(key, obj[key]);

}

// name amy 
// age 29 
// email wlgysdl3@naver.com
```
<br>
## 스코프 & 클로저

### 스코프

유효 범위라고도 부르며 변수가 어느 범위까지 참조되는지 뜻한다.

전역 스코프, 지역스코프로 나뉨

var 을 사용하면 안되는 이유!!

var 을 사용하면 호이스팅 되어, 변수선언이 함수 상단으로 올라가게됩니다.

그래서 블록 내부에 새롭게 선언하더라도, 블록 외부 변수 값도 변하게 됩니다.

이런 차이가 발생하는 이유는, var 는 함수수준의 스코프이고 const 와 let 은 블록 수준 스코프이기때문입니다. 따라서 var는 개발자가 오류를 찾기가 힘들어집니다. 

### 클로저

함수가 선언된 환경의 스코프를 기억하여 함수가 스코프 밖에서 실행 될 때에도 기억한 스코프에 접근할 수 있게 만드는 문법

중첩함수

- 상위 스코프의 식별자를 참조하고 있고
- 본인의 외부 함수보다 더 오래 살아있다면

**내부 함수는 생명주기를 마감하고 실행 컨텍스트 스택에서 전부 사라졌지만, 내가 기억하고 있는 내부 슬롯에 저장된 상위 스코프에 의존하여 상위 스코프 내의 식별자를 참조할 수 있는 것이다.**

→ 클로저를 잘 알아야하는 이유는 유용하게 사용하기보단 **알기 힘든 버그를 잘 수정하기 위해**서다

### 은닉화

클로저를 이용하여 내부 변수와 함수를 숨길 수 있다.
