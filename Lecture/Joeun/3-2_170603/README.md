# FAST Campus HTML & CSS Camp Day 6
* 6월 6일 (휴강)
* 유튜브 과제는 다음 주 토요일

## Create Amazing HTML Form
* Form
    * 유저 : 유저가 데이터를 입력할 수 있는 모든 HTML
    * 사이트 : 유저에게 데이터를 입력받는 모든 HTML
* FORM 구성요소
    * form
        * 전체 입력의 처리
        * 전송, reset 범위, 전송할 때 형태
        * 백엔드
        * form에 CSS를 direct로 넣지 않음
    * input
        * 실제로 유저에게 입력받는 요소
        * 아주 많은 type을 가지고 있음
            * `type="text"`
            * `type="url"`
            * `type="number"`
                * 입력이 숫자만 가능 (OS 레벨)
            * `type="tel"`
                * 숫자만 있는 키패드
            * `type="email"`
            * `type="date"`
            * `type="time"`
            * `type="password"`
            * `type="checkbox"`
                * 여러개의 선택지 중 여러개를 선택
            * `type="radio"`
                * 여러개의 선택지 중 하나만 선택
        * placeholder
            * 힌트 텍스트
            * 이 속성값을 label의 목적으로써 사용하지 말 것
            * ID : <input type="text" placeholder="baemin@baemin.com 혹은 apes0123">
            * IE에서 지원하지 않음
        * required
            * 필수값
            * IE에서 지원하지 않음
        * name
            * 서버에서 실제로 받을 때
            * radio 버튼이나 checkbox 같은 경우에는 name 속성값으로 그루핑
        * autocomplete
            * name (이름)
            * given-name (이름)
            * additional-name (중간 이름)
            * family-name (성)
        * minlength, maxlength
        * disabled
            * 사용 불가능하게 (Input을)
        * readonly
            * 읽기전용
    * Input (Status)
        * :required {}
        * :invalid {}
        * :valid {}
        * :optional {}
        * :checked {}
        * :disabeld {}
    * select
    * label
        * 이 Input 혹은 Select가 어떤 데이터를 받을 것인 지 설명
(1) 
```
[CSS]
label {}
label:before {}
label:after {}
label input {}
[HTML]
<label>비밀번호: <input type="password"></label>
```

(2) BETTER GOOD
```
[CSS]
label {}
label:before {}
label:after {}
input {}
label ~ input {}
input ~ label {}
input:checked ~ label {}
input:disabled ~ label {}

[HTML]
<label for="pwd">비밀번호</label>
<input id="pwd" type="password">
```

### Reference
* https://developers.google.com/web/fundamentals/design-and-ui/input/forms/

## CSS Position
* 배치
* static (정적)
    * Normal Flow
    * 내가 flow를 수정하고 싶어도 수정 불가능한 상태
* Position을 사용하는 속성
    * 아래 속성들을 사용하면 position container가 되고
    * 특정한 좌표값의 루트로써 활용
    * box offset 속성을 사용할 수 있게됨
    * box offset
        * left
        * top
        * right
        * bottom
        * z-index
    * relative
        * 겉보기에는 Static
    * absolute
        * 절대값 배치
    * fixed
        * 스크롤을 하던말던 계속 고정
    * sticky
        * 원래 위치에 있다가 브라우저가 해당 요소의 위치에 스크롤이 도달하면 fixed
        * IE 빼고 다 지원

## CSS Flexbox
* 레이아웃을 만듦
    * Flexible Box
    * 자유자재로 늘어나거나 줄어드는 Layout
* flexbox
    * 요소의 순서를 바꿀 수도 있고
    * 요소가 자기 알아서 늘어나거나 줄어들도록
    * IE 지원율 X
    * Andorid 2.x 지원율 X

## CSS Values & Units (Next)

## Codelabs
* 실습
* gulp + express
    * gulp-express (없어짐)
    * express 기반
* Youtube
    * 비디오? (iFrame)
    * 레이아웃?
        * 특정 사이즈를 기준

---

내 메모

HTML/CSS 170603

iOS Simulator를 통해서 모바일 환경에서 form의 input을 확인해볼 수 있어요

접근성을 고려한다면 placeholder가 아닌 label 태그를 활용할 것
(홈페이지를 입력해주세요 라고 할 것이라면, 원래는 https:// facebook.com 의 형태가 적합함, 실제로 들어갈 데이터에 대한 힌트 텍스트이기 때문에)

label의 for는 input의 id와 연결시키는 역할
<label for="pwd">비밀번호: </label>
<input id="pwd" type="password">

label의 HTML상 위치와 상관없이 우리가 기대하는 화면이 나옴

ID 관련해서 placeholder를 사용할 때, 아이디를 입력해주세요 라는 placeholder 대신 아이디의 형태에 대한 힌트를 줄 것(요새는 아이디가 일반 아이디도 있고, 이메일 아이디도 있기 때문에 힌트가 소중, baemin@baemin.com)

placeholder와 required는 IE에서 지원하지 않기 때문에 별도의 JS 검사가 필요

radio 여러 개 중에 하나만 선택해야 할 때(피자 도우, 버튼간 연관성은 name 속성을 부여해주어야 함)

레이블을 눌렀을 때 선택되려면 label for와 input의 id를 통일

required된 요소들이 완성될 때까지 form에 disabled 속성을 부여하는 것을 통해 submit을 못하게 하는 것도 가능

normal flow : 세로로 쌓이는 구조

box offset 요소를 통해 다른 요소에 영향을 주지 않고 움직일 수 있다

left와 right가 모두 0이면 그것을 연결해서 해당 가로를 모두 차지하게 됨(세로도 마찬가지)

fixed는 부모가 아닌 브라우저를 기준으로 함

markup순서가 뒤에 있다면 암묵적으로 z-index가 더 높다고 처리됨
모두 z-index가 1이지만, 실질적으로는 1.x으로 작용하는 것

transition, flexbox가 css 관련 큰 사건들

flexbox : 유동형 레이아웃
(요소의 순서를 바꾸거나, 알아서 늘어나거나 줄어들도록 함)
container와 item이 존재
container에 display: flex; 를 줘야 함
item에 flex 속성을 이용해서 분할 가능

flex-wrap으로 주면 포함할 수 있는 아이템의 개수가 초과했을 때 아이템을 줄바꿈하도록 할 수 있다(min-width를 필요로 함)

justify-content : 요소의 메인 축 정렬
align-items : 요소의 서브 축 정렬

flex-direction을 통해 쌓이는 방향을 바꿀 수 있음

Flexbox는 IE는 거의 지원하지 않는다고 보셔야 해요

youtube 과제
- video는 iframe (youtube copy embed code)
- layout은 특정 사이즈를 기준
- position, font 등도 포함
- validator

최대한 공통적인 요소를 먼저 짜세요
큼직한 것들부터 짜세요
디테일은 나중에 신경쓰세요
