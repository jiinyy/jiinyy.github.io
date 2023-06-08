## 브라우저에 URL을 입력하면 무슨 일이 발생할까요?

1. URL 을 해석합니다. ( URL은 스키마, 계정정보, 호스트, 포트와 같은 정보로 이루어져있다)
2. DNS를 조회합니다. (Domain Name System)
3. 해당 IP 가 존재하는 서버로 이동합니다. ( 예 . 한국에서 미국에있는 서버를 요청할 경우, 네트워크 장비인 라우터를 통해 해당 서버가 존재하는 영역으로 접근함)
4. ARP 를 이용하여 MAC 주소 변환을 합니다. (IP=논리적인 주소, MAC=물리적인 주소) 기계의 실제 위치를 알기 위해서는 MAC 주소가 필요합니다. 경복궁의 주소를 생각해보세요. 경복궁의 주소= 서울 종로구 사직로 161 주소가 바뀐다면 그 후에 이 위치를 제대로 알 수 있을까요? 
5. TCP 통신을 통해 Socket을 열어야 합니다. 
6. 서버는 응답을 반환합니다. (HTTP 프로토콜로 들어온 패킷을 읽고 처리한다.)
7. 브라우저는 렌더링합니다. ( HTML을 읽어 DOM Tree 를 구축한다. 만들어진 Dom Tree를 이용하여 화면에 그린다.)

## **HTTP와 HTTPS의 차이점은 무엇인가요?**

HTTP(Hypertext Transfer Protocol)는 클라이언트와 서버 간 통신을 위한 통신 규칙 세트 또는 프로토콜입니다. 사용자가 웹 사이트를 방문하면 사용자 브라우저가 웹 서버에 HTTP 요청을 전송하고 웹 서버는 HTTP 응답으로 응답합니다. 웹 서버와 사용자 브라우저는 데이터를 일반 텍스트로 교환합니다. 간단히 말해 HTTP 프로토콜은 네트워크 통신을 작동하게 하는 기본 기술입니다. 이름에서 알 수 있듯이 HTTPS(Hypertext Transfer Protocol Secure)는 HTTP의 확장 버전 또는 더 안전한 버전입니다. HTTPS에서는 브라우저와 서버가 데이터를 전송하기 전에 안전하고 암호화된 연결을 설정합니다.

HTTP는 암호화되지 않은 데이터를 전송합니다. 즉, 브라우저에서 전송된 정보를 제3자가 가로채고 읽을 수 있습니다. 이는 이상적인 프로세스가 아니었기 때문에, 통신에 또 다른 보안 계층을 추가하기 위해 HTTPS로 확장되었습니다. HTTPS는 HTTP 요청 및 응답을 SSL 및 TLS 기술에 결합합니다.

> 함수형 프로그래밍
> 

### 프로그램은 순차, 분기, 반복, 참조로 구성된다.

패러다임은 이 4가지 요소를 어떻게 이용할 것인가를 다룬다.

객체지향 :  객체라는것을 통해 데이터와 메서드를 묶고, 객체 간 통신을 함으로써 프로그램이 작동함

함수형 :  데이터를 함수로 이용해 새로운 데이터를 만들어 나가는 데이터 파이프 형태로 프로그램이 작동함

- 객체지향 추상화의 최소 단위 = 객체, 함수형은 함수가 최소 단위다.
- 함수 단위로 나눠지므로 재사용성이 높다
- 데이터의 불변성을 지향함. 동작을 예측하기 쉬움. 사이드 이펙트를 방지하는 장점이 있음. → 스레드들을 통한 동시성 문제도 해결함
- 객체지향은 순차, 분기, 반복, 참조를 전환을 객체를 통해 간접으로 통제하고, 함수는 변수할당을 통제하여 4가지 제어흐름을 통제한다고 볼수있음.
- 선연형 프로그래밍과 가깝다.
    - 선연형 프로그램이란..?
        
        객체 지향이나 함수형처럼 설계에 대한 패러다임이 아닌, 사고에 대한 패러다임이라 볼 수 있습니다. 기존 명령형 프로그램은 문제를 어떻게 해결해야될지, 컴퓨터에 명령을 내리는 사고방식이라고 생각할 수 있습니다. 반면 선언형 프로그래밍은 무엇을 해결해야될지에 집중하고, 해결방법은 컴퓨터에 위임하는 방법입니다.
        
        `명령형`
        
        ```jsx
        let a = [1,2,3,4,5];
        for (let i = 0; i < 5; i += 1) {
        	if(a[i] % 2 === 0) {
        		console.log(a[i]);
        	}
        }
        ```
        
        변수를 선언하고, 데이터를 데입한 후 루프를 돌면서 조건에 따라 출력한다. 라는 명령을 내립니다. 
        
        `선언형`
        
        ```jsx
        [1,2,3,4,5]
        	.filter((item) => item % 2 === 0)
        	.forEach((item) => console.log(item));
        ```
        
        반대로 선언형 코드는 먼저 무엇이 필요한지 분석해야합니다. 데이터중 짝수만 걸러내는것이 필요하고, 출력하는 것이 필요합니다. 필요한 요구사항만 구현하여 사용하면 데이터는 자동으로 원하는 결과값으로 출력됩니다.
        
        장점
        
        - 상태가 없기 때문에 사이드 이펙트가 없음.
        - 함수단위로 나눠지기 때문에 재사용성이 높다
        - 함수의 조합을 통해 코드가 짧고 간결하다
        
        단점 
        
        - 상태가 없다는 것은 변수 조작이 안된다는 뜻. 만약 게임을 할때 상대방 캐릭터가 나를 공격했다면 어떻게 할까요? 객체 지향 프로그래밍에서는 단순히 체력과 관련된 변수를 감소시키기만 하면됩니다. 하지만 함수형 프로그래밍에서는 상태를 조작할 수 없기 때문에, 다른 방법을 찾아야합니다. 그 방법은 캐릭터와 관련된 데이터에서 체력을 깎은 채로 복사한 후, 기존 캐릭터와 교체하면 됩니다. 이 방법은 쓸데없이 메모리와 성능을 사용하기때문에 이런경우에 함수형 프로그래밍에 단점이 됩니다.
        - 코드가 짧고 간결하려면 많은 숙련도를 요구합니다.
        
        ```jsx
        //객체지향 프로그래밍
        function StringNumber(string) {
        this.string = string;
        }
        StringNumber.prototype.calculate = function () {
        const stringNumber = "12345";
        this.sum = 0;
        for (let i = 0; i < stringNumber. length; i += 1) {
        this.sum += stringNumber[i] - "0";
        };
        const stringNumber = new StringNumber ("12345");
        const printer = new Printer();
        stringNumber.calculate ();
        printer. log(stringNumber.sum);
        ```
        
        → 숫자형태 문자열을 담고있는 객체가 있고, 이 객체는 계산하여 합을 구해주는 계산을 부여받았습니다. 그리고 계산한 값은 객체에 저장됩니다. 값을 출력하는 일은 다른 역할이기 때문에 프린터 객체가 담당하게 되고, 단순히 stringNumber 객체는 자신의 값을 프린터로 넘기고 출력됩니다. 
        
        ```jsx
        //절차지향 프로그래밍
        const stringNumber = "12345";
        let sum = 0;
        for (let i = 0; i < stringNumber. length; i += 1) {
        sum += stringNumber[i] - "0"
        }
        ```
        
        → 공유데이터인 stringNumber 와, sum 변수가 있습니다. 이를 반복문을 통해 조작해줍니다. 이 로직은 함수로 만들수도있습니다. 오히려 이런 간단한 문제에서는 절차지향이 편합니다. 
        
        ```jsx
        //함수형 프로그래밍
        const stringNumber = "12345";
        console. log( stringNumber .split('')
        .map(x => parseInt (x))
        . reduce ( (x, y) => x + y, 0);
        );
        ```
        
        → 함수형 프로그래밍은 데이터를 모두 함수로 실행해 연속으로 만들어냅니다.
        
        먼저 문자열을 자르는 함수(split), 이어서 정수로 바꿔주는 함수(parseInt), 각 요소를 합해주는 함수(map), 출력해주는 함수 이렇게 조합하여 결과를 도출합니다. 
        
        **JavaScript 는 멀티 패러다임이 가능합니다. 굳이 객체지향과 함수형으로 나눌 필요는 없다. 둘다 같이 쓰자!**
        
        > 객체 지향과 프로토타입
        > 
        
        ### 객체지향의 객체란..?
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/17938b42-244b-4422-a39f-7c7f8bb6380a/Untitled.png)
        
        현실 버튼 
        
        - 튀어나와있다,
        - 누르면 무언가 발생한다
        - 실제로 만질 수 있다
        - 고장날 수 있다
        - 스프링이 필요하다
        - 색을 입힐 수 있다.
        
        웹 사이트 버튼 
        
        - 튀어나와있다
        - 누르면 무언가 발생한다
        - 색을 입힐 수 있다
        
        **객체지향의 객체는 현실에 있는 것을 추상화 한 것! (현실에 존재하는 것을 코드로 옮긴는 것이 아니다!)**
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2af80e42-6a5b-4c2e-a567-6969e94ca61e/Untitled.png)
        
        추상이란 사물이 지니고 있는 여러 측면 중 특정한 부분만 보는 것 ( 그 외에 필요없는 부분은 전부 버린다!)
        
        ### 객체 지향이란..?
        
        - 객체 위주로 설계하고 프로그래밍하는 패러다임
        - 객체지향 언어에선 추상화의 최소 단위가 객체다
        - 각각의 객체는 메시지를 주고받을 수 있다.
            - 절차지향은 공유데이터를 각 함수가 절차적으로 직접 통제했다면, 객체지향은 객체가 데이터를 관리하고, 각각 메세지를 통해 간접적으로 통제합니다.
        
        ### 객체지향의 오해
        
        C 언어에서는 객체지향 프로그래밍이 불가능하다?
        
        흔히 C 언어는 절차지향언어 /  C++ 객체지향언어 라고 착각하지만, 패러다임과 언어는 동일한 것이 아닙니다. 언어는 지향하는 패러다임을 조금 더 편하게 쓸 수 있게 해줄뿐, 다른 패러다임이 불가능 한 것은 아닙니다. class 가 없는 JavaScript 나 Go, C 언어도 객체지향 프로그래밍을 할 수 있습니다. **자바스크립트는 프로토타입을 통해 객체지향을 표현한다.**
        
        절차지향보다 객체지향이 무조건 더 좋은 것은 아닙니다.
        
        만들어야하는 프로그램에 따라 절차지향이 더 적합할 수 있고, 비교적 간단한 프로그램일 수록 절차지향이 더 만들기 쉽고 직관적입니다.(예,계산기)
        
        객체지향은 객체간 통신하기 때문에 흐름에 더 직관적이어서 더 복잡한 프로그램에 적합합니다. 
        
        ### 프로토타입
        
        자바스크립트의 객체는 클래스 기반 언어처럼 속서(Attribute) 와 행위 (Method)를 정의할 수 있습니다. 
        
        ```jsx
        //객체 리터럴
        const person = {
        	name: "이선협"
        	company: "코발트"
        	move: function (destination) {
        		console.log(`${destination}(으)로 이동합니다.`);
        	),
        },
        
        //Object 생성자 함수
        const person = new Object ();
        person. name = "이선협" ;
        person. company = "코발트";
        person.move = function (destination) {
        	console.log(`${destination}(으)로 이동합니다.`);
        };
        
        //생성자 함수
        function Person(name, company, move) {
        	this.name = name;
          this.company = company;
          this.move = function (destination) {
            console.log(`${destination}(으)로 이동합니다.`);
        	);
        };
        ```
        
        ### 객체지향 Class 문법 (feat. 애플코딩)
        
        ```jsx
        var nunu = {
        	q : 'consume',
        	w : 'snowball'
        }
        
        var garen = {
        	q : 'strike',
        	w : 'courage'
        }
        ```
        
        ```jsx
        function 기계() {
        	this.q = 'consume';  // 새로 성성되는 object(instance)에 {q:'consume'} 을 추가해주세요
        	this.w = 'snowball'; // 새로 성성되는 object(instance)에 {W:'snowball'} 을 추가해주세요
        }
        
        new 기계(); // 기계에서부터 새로운 object 를 뽑고싶다.
        var nunu = new 기계(); 
        var garen = new 기계();
        ```
        
        비슷한 object 많이 만들일 있으면 class 를 만들어 쓰면 됩니다.
        
        (class 는 object 뽑는 기계일뿐)
        
        여기서 this 라는게 존재하는 이상, 기계() 는 class 역할을 대신해줄수있다
        
        this = 기계로부터 생성되는 object = instance
        
        하지만 여기서 이상한 점이 있다.
        
        nunu 의 객체는 {q:'consume'},{W:'snowball'} 로 잘 나오지만, 
        
        garen 의 객체도 똑같이 나온다.
        
        이럴때 사용하는게 parameter 다.
        
        ```jsx
        <script>
        
        function 기계(구멍) {
        	this.q = '구멍';  // 새로 성성되는 object(instance)에 {q:'consume'} 을 추가해주세요
        	this.w = 'snowball'; // 새로 성성되는 object(instance)에 {W:'snowball'} 을 추가해주세요
        }
        
        new 기계(); // 기계에서부터 새로운 object 를 뽑고싶다.
        var nunu = new 기계('consume'); // 기계 {q:'consume', w:'snowball'}
        var garen = new 기계('strike'); // 기계 {q:'strike', w:'snowball'}
        
        </script>
        ```
        
        ES6 class 신문법을 사용해보자 (2016년 이후 가능)
        
        ```jsx
        <script> 
        
        class Hero {        // class명을 정할때는 영어대문자로 작명함
        	constructor(구멍) {
        		this.q = '구멍';  
        		this.w = 'snowball';
        	}
        }
        
        new Hero();
        
        </script>
        ```
        
        여기서 function,class 부분은 부모, new 새로운 object 를 뽑아낸 부분은 자식이라고 표현하기도 한다.
        
        부모/자식 상속을 구현할 수 있는 prototype 이라는 이상한 문법도 있다.
        
        > 이거보고 prototype 이해 못하면 강의접음(feat.애플코딩)
        > 
        
        prototype 이라는거 써도 자식 object에게 데이터 물려줄 수 있다
        
        콘솔창에 기계.prototype 을 입력해보면 {constructor :f} 라는게 뜬다
        
        이처럼 기계는 자동으로 prototype 이라는 공간이 생긴다.
        
        prototype = 유전자다
        
        우리가 키가 작은 이유는?
        
        부모님 탓입니다. 부모님이 물려주셨기 때문입니다.
        
        ```jsx
        <script>
        
        function 기계(구멍) {
        	this.q = '구멍';  
        	this.w = 'snowball'; 
        }
        
        기계.prototype.name = 'kim';
        
        var nunu = new 기계 ('strike');  // nunu.name = "kim" , nunu = 기계 {q:'strike', w:'snowball'}
        
        </script>
        ```
        
        부모에서 프로토타입을 사용해 name 은 무엇이다 설정을 하면, 자식이 사용할수있다
        
        즉, function 안에 작성하면 자식이 직접 가지고 있다.
        
        프로토타입 즉 유전자에 추가를 해주면 부모만 가지고 있다고 보면된다.
        
        ### 부모 유전자에 있는 걸 자식이 사용가능한 이유는…?
        
        자바스크립트는 이런 원리로 동작을 하기때문입니다.
        
        object 에서 자료 뽑고싶을 때, [nunu.name](http://nunu.name) 이런식을 이용하여 뽑습니다.
        
        nunu 가 name 을 가지고 있으면 출력을해주지만, name 을 가지고있지 않은 경우, 컴퓨터는 여기서 포기하지 않고, 부모 유전자에게 물어봅니다. 
        
        거기에 name 이 있다면 출력을해줍니다. 만약 거기에도 없다?
        
        부모의 부모 유전자까지 가서 물어봅니다.
        
        이것을 전문용어로 prototype chain 이라고 합니다.
        
        이 원리를 이해했다면 좀 더 넓은 개념으로 생각 해 볼수있습니다!
        
        ```jsx
        <script>
        
        function 기계(구멍) {
        	this.q = '구멍';  
        	this.w = 'snowball'; 
        }
        
        기계.prototype.name = 'kim';
        
        var nunu = new 기계 ('strike');
        
        var arr = [4,2,1];
        arr.sort(); // 데이터 정렬이가능함
        </script>
        ```
        
        arr.sort(); 
        
        여기서 array 에 붙일 수 있는 기본함수가 있다.
        
        여기서 array 자료에 sort(); 를 붙일 수 있는 이유가 뭘까요?
        
        ```jsx
        var arr = [4,2,1];   // 인간의 방식
        var arr = new Array(4,2,1);  // 컴푸터 방식
        ```
        
        new 키워드 오른쪽에 기계이름을 적으면 이 기계로부터 자식을 하나 뽑아줍니다
        
        그것을 변수에 담아서 쓰는거구요 
        
        그렇다면 다시 돌아가 arr.sort(); 를 쓸 수 있는 이유는 뭘까요?
        
        Array 라는 부모 유전자에 기록이 되어있으니 쓸 수 있는겁니다.
        
        Array.prototype 이라고 출력을 해보면 안에 여러가지 항목들이 나옵니다. (filter, map, push, pop, length) 등
        
        ### 모든 array 자료에서 쓸 수 있는 함수 추가는 어떻게 할까요?
        
        ```jsx
        Array.prototype.함수 = function(){};
        ```
        
        Array prototype 을 수정하는 문법입니다. 
        
        거기에 함수 하나 추가해주세요 라는 문법 입니다.
        
        ### 이벤트 루프
        
        JavaScript 는 대표적인 Single Thread 언어이다?
        
        JavaScript 의 Call Stack 은 하나만 존재합니다. 그래서 실제로 Single Thread 로 동작합니다.
        
        ### 그렇다면 브라우저에서 실행되는 script 는 어떻게 비동기적으로 데이터를 불러오고 애니메이션을 실행시킬까요? 어떤 원리로 애니메이션과 클릭이벤트를 같이 처리할 수가 있는 걸까요?
        
        그것은 브라우저에 이벤트루프 라는 시스템이 있기 때문입니다.
        
        간혹 이벤트루프가 자바스크립트의 기능이라 생각하시는 분이 계시는데 이벤트루프는 자바스크립트 엔진에 포함되어있지 않습니다. 
        
        브라우저나 node.js 에서 자체적으로 관리를 하고 있습니다.
        
        Web APIs ( DOM Events, AJAX, TIMER) = 브라우저에서 제공하는 API 입니다.
        
        Click 과 같은 DOM 이벤트나, 네트워크 호출, 타이머 등은 실행시킬 때 브라우저에 위임됩니다. 
        
        > 콜백함수가 뭔지 한국어로 쉽게 설명하는 영상(feat.코딩애플)
        > 
        
        ### 콜백함수
        
        정의 : 함수에 파라미터로 들어가는 함수 
        
        용도 : 순차적으로 코드를 실행하고 싶을 때
        
        ```jsx
        <script>
        
        document.querySelector.('.button').addEventListener('click', function () {
           dfdfdfdfdfdf
        });
        
        // setTimeout 는 1초후에 이런 코드 실행시켜주세요 라는 함수이다
        setTimeout(function 함수명(){ 
        	wewewewe
        },1000)
          
        
        </script>
        ```
        
        addEventListner = 함수
        
        function () { dfdfdfdf } = 콜백함수
        
        버튼을 클릭했을 때, dfdfdfdfdf 코드가 실행됨 (용도 : 순차적으로 코드가 실행됨)
        
        [참고] 콜백함수 function () { dfdfdfdf } 에는 다른데서 만든 함수도 콜백함수로 넣을 수 있다. 
        
        [참고2] 콜백함수에 함수명 쓸데없이 작명할 수 있다.
        
        Q. first() 함수 다음에 second() 함수를 실행하고 싶다면..?
        
        ```jsx
        <script>
        
        function first(파라미터){
        	console.log(1)
        	파라미터()
        }
        
        function second() {
        	console.log(2)
        }
        
        first(second)
        
        </script>
        
        ```
        
        하지만 이러한 방법으로 콜백함수를 만드는 건 쓸데가 없어보입니다.
        
        first()
        
        second()
        
        이렇게 써도 결과는 똑같기 때문이죠 (자바스크립트는 위에서 부터 한줄한줄 실행되기 때문에)
        
        하지만, 이렇게 쓸때가 가끔 있기는 합니다.
        
        예를 들면 협업을 할때, 어떤사람이 first라는 함수를 만들었다고 생각을 해 봅시다
        
        팀원들이 자주 쓰는 것이고, 이 함수를 다른 팀원들이 갖다 쓴다고 합시다
        
        팀원1 :  first() 후에 console.log(2) 를 바로 하고 싶어요
        
        팀원2 :  first() 후에 console.log(4) 바로 하고 싶어요
        
        first()
        
        console.log(2) 를 해도 순차적으로 실행은 되겠지만
        
        약간 불안해요. first() 함수가 갑자기 비동기 처리가 되면 뒤에 console.log(2) 는 실행되지 않으니까요.
        
        그렇다면 어떻게해야될까요?
        
        first() 함수를 업그레이드 시켜 놓으면 되는 겁니다. 
        
        이때 콜백함수를 씁니다.
        
        ```jsx
        <script>
        
        function first(파라미터){
        	console.log(1)
        	파라미터()
        }
        
        function second() {
        	console.log(2)
        }
        
        first(second)
        
        </script>
        ```
        
        콜백함수를 너무 많이 쓰면 단점이 보입니다.
        
        콜백함수를 많이 쓰는 경우는 ‘(코드에서) DB에서 데이터를 뽑고 싶을 때’ 인데요
        
        자바스크립트를 이용하여 DB 데이터를 뽑을 수도 있어요
        
        근데 만약에 A 데이터를 뽑고,  그 다음 B를 뽑고, 그 다음 C 를 뽑고 싶다고 가정해봐요
        
        ```jsx
        <script>
        db.collection('post').findOne(A, function(){
        	db.collection('post').findOne(B, function(){
        		db.collection('post').findOne(C, function(){
        		})
        	})
        })
        </script>
        ```
        
        이런식으로 코드를 짜면 코드가 너무 길어집니다
        
        이런식으로 짜기가 싫다 (콜백함수를 이용하기 싫다) 하시면 콜백함수로 디자인하지 말고 Promise 도 있습니다.
        
        ```jsx
        <script>
        
        function first(파라미터){
        	console.log(1)
        	파라미터()
        }
        
        function second() {
        	console.log(2)
        }
        
        first().then()
        
        </script>
        ```
        
        then() 을 사용하여 코드를 순차적으로 실행할 수도 있습니다.
        
        Promise 도 복잡해서 싫다 그러면 async, await 을 쓸 수도 있습니다.
        
        > JavaScript - async & await (feat.생활코딩)
        > 
        
        ```jsx
        timer(1000,function(){
        	console.log('작업');
        	timer(1000,function(){
        		console.log('작업');
        		timer(1000,function(){
        			console.log('작업');
        		});
        	});
        });
        ```
        
        ```jsx
        timer(1000)
        	.then(function(){
        		console.log('작업')
        		return timer(1000);
        })
        	.then(function(){
        		console.log('작업')
        		return timer(1000);
        })
        	.then(function(){
        		console.log('작업')
        		return timer(1000);
        })
        
        ```
        
        위의 두개의 코드는 똑같이 동작하는 코드지만, 오른쪽 코드에는 promise 가 적용된 코드이다.
        
        then 을 통해 체이닝 되니까 왼쪽의 코드처럼 함수안에 함수가 들어가는 또 그안에 함수가들어가는 callback 헬로우부터 벗어나게 되었습니다.
        
        ```jsx
        timer(1000)
        	.then(function() {
        			console.log('작업')
        			return timer(1000);
        	})
        	.then(function(){
        		console.log('작업')
        		return timer(1000);
        })
        .then(function(){
        	console.log('직업')
        })
        ```
        
        ```jsx
        async function run(){
        	await timer(1000)
        
        			console.log('작업')
        	await timer(1000)
        
        			console.log('작업')
        	await timer(1000)
        
        			console.log('작업')
        }
        run();
        ```
        
        위의 두개의 코드는 똑같이 동작하는 코드이지만, 오른쪽에는 async 와 await 이 들어간 함수이다. await = 비동기적인 함수 앞에 이 함수가 실행하기를 기다려라. 라는 뜻에서 앞에 await 을 붙입니다. 그리고 한가지 더 제약사항이 있는데, await 가 붙어있는 promise 를 리턴하는 함수는 반드시 다른 함수 안에서 실행되야해요. 그리고 그 함수는 앞에 async 라는 키워드가 앞에 붙어있어야합니다.  마지막으로 실행은 run(); 을 작성하여 실행하면됩니다. 
        
        ### 모듈
        
        모듈 vs 컴포넌트
        
        모듈 =  설계 시점에 의미있는 요소
        
        컴포넌트 = 런타임 시점에서 의미있는 요소
        
        즉 모듈의 우리가 의식적으로 나눠놓은 요소, 컴포넌트는 나눠놓은 요소에 포함되어 실행되는 요소이다 
        
        디렉토리 단위를 모듈개념에 가깝게 사용하는 경우가 많다
        
        모듈은 로컬 파일에서 동작하지 않고 HTTP 또는 HTTPS 프로토콜을 통해서만 동작하기 때문에 서버를 실행시킬 필요가 있습니다.
        
        `모듈 기초사용방법`
        
        `hello.js`
        
        ```jsx
        export function hello(name) {
        		alert(`Hello, ${name}!`);
        }
        ```
        
        `index.html`
        
        ```html
        <body>
        	<script type="hello">
        		import { hello } from './hello.js';
        	
        		hello('John');
        	</script>
        </body>
        ```
        
        스크립트 속성으로 타입이 모듈로 되어있음
        
        그러면 이 스크립트는 모듈로 동작한다는 의미.
        
        모듈로 동작하게 되면 Import 를 통해 다른 파일을 불러올 수 있음
        
        여기에선 hello.js 를 불러옵니다.
        
        hello.js 에서는 hello 라는 함수를 내보내고 있음
        
        내보낸 hello를 import 하고 실행하면 브라우저에서 정상적으로 실행된 것 을 확인할 수 있다. 
        
        alert = Hello John!
        
        ### 모듈의 특징
        
        1. 항상 use strict 로 실행된다 : 일반 스크립트는 let 이나 var 을 생략하고 변수선언이 가능합니다. 이 경우 전역 스코프에 저장됩니다.  반면 모듈 스크립트는 엄격모드로 동작하기 때문에 허용되지 않습니다. 
        2. 모듈 레벨 스코프가 있다 : 모듈은 최상위에 변수를 선언하더라도 전역스코프에 올라가지 않고 자체적이 모듈레벨 스코프에 올라갑니다. 일반 스크립트는 최상위에 선언하면 전역 스코프에 선언되어 다른 스크립트에서도 참조가 가능하지만 모듈 스크립트에선 import 를 하지 않는 한 서로 참조가 불가능 합니다. 
        3. 단 한번만 평가된다 :  두번 import 되더라도 실행은 단 한번만 됩니다. 만약에 여기서 내보내기를 하더라도 이미 평가된 것을 불러와서 사용하기만 할 뿐입니다. 
        4. 지연 실행이 된다 :  일반 스크립트는 바디 태그에 넣을 경우 순서에 따라 돔이 생성되기 전에 실행될 수 있습니다. 하지만 모듈 스크립트는 defer 옵션을 넣지 않아도 자동으로 지연실행이 됩니다. 그래서 모든 돔이 만들어 진 후에 실행이 됩니다. 
        
        하지만 요즘은 Webpack 과 같은 모듈 번들러를 사용하기 때문에 크게 모듈 스크립트를 사용할 일이 많지 않습니다. 번들링 한 스크립트 하나만 불러오면 끝이니까요 
        
        ### 유니코드
        
        ### 정규표현식
        
        010-3333-4444 → 01033334444
        
        로 바꿔서 백엔드로 보내야할때 정규표현식을 씀
        
        ### 쿠키와 세션, 웹 스토리지
        
        클라이언트가 아무리 쿠키를 보내도 서버에서는 그 쿠기의 주인이 누군지 모른다.
        
        이 주인을 알 수 있도록 하려면 어떻게 해야될까요?
        
        정답은 Session(세션) 입니다.
        
        쿠키의 http Session id 를 식별자로 담아 클라이언트와 서버 간 통신이 가능합니다.
        
        서버는 식별자로 사용자를 구분하고 적절한 데이터를 응답합니다.
        
        ### 세션의 문제점
        
        - 세션은 서버에 파일로 저장됨. 만약 사용자가 엄청 많다면? - 메모리 폭발
        - 서버가 만약 2대라면 세션은 어떻게 관리 해야할까? - 각 인증 번호가 퍼져있어서 제대로 된 정보를 응답하지 못할수도있음
        
        서버와 클라이언트간 인증은 별도 토큰 사용
        
        쿠키는 클라이언트 자체적인 지속적인 데이터 관리 용도로 사용 
        
        이런 상황에서 새로운 표준이 등장했습니다. 
        
        쿠키 대신 로컬 데이터를 관리하는 웹 스토리지 입니다
        
        > 로컬 스토리지
        > 
        - 로컬 스토리지에 데이터를 저장하면 반영구적으로 데이터가 저장된다
        - 브라우저를 종료해도 계속해서 데이터가 남는다
        - 저장했던 도메인과 이용하는 도메인이 다른 경우엔 접근할 수 없다.
        - 쿠키와 마찬가지로 Key-Value 형태로 저장한다
        
        > 세션 스토리지
        > 
        - 새 창을 생성할 때마다 개별적으로 저장되는 데이터를 관리한다.
        - 브라우저를 닫는 순간 사라진다
        - 같은 도메인이어도 세션이 다르면 데이터에 접근할 수 없다
        - 쿠키와 마찬가지로 Key-Value 형태로 저장한다.