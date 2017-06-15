# HTML Elements (1 hour 30 min)
## Sections
* HTML의 문서적 의미
### section
* The section element represents a generic section of adocument or application.
* 그럼 div와 차이가 뭘까?
* 구획, 특정 영역
* Outline (특정 관심사의 유효범위)
* section 요소는 반드시 제목(h1-h6)이 있어야함 
* outline 알고리즘이 적용됨
  * sectioning contents 전체에 적용이 됨 (article aside nav section)
  * sectioning 콘텐츠 밑에 다른 sectioning 요소가 
  있다면 h1만 써줘도 알아서 레벨이 낮아짐
  * 구버전의 브라우저는 아웃라인 알고리즘을 지원하지 않아요 (IE)
```
<section>
    <h1>Movie</h1>
    <p>blah blah blah</p>
    <section>
        <h2>Sports</h2>
        <p>Blah Blah Blah</p>
    </section>
    <p>캐리비안의 해적 - 개봉</p>
</section>
```
```
잘못된 예시:)
<div class="news-area">
    <h1>Movie</h1>
    <p>blah blah blah</p>
    <div>
        <h2>Sprots</h2>
        <p>Blah Blah Blah</p>
    </div>
    <p>캐리비안의 해적 - 개봉</p>
</div>
```

### article
* 근본적으로는 Section과 동일
* 독립적인 콘텐츠
* RSS 피드 (블로그 글)
* 위젯
* article의 section의 합집합

```
<section>
    <h1>개발자들이여 공부하라</h1>
</section>
```

```
<article>
    <h1>개발자들이여 공부하라</h1>
</article>
```

### aside
* 사이드
* 전의 콘텐츠를 부가적으로 설명하는 콘텐츠
* 있어도 그만 없어도 그만인 컨텐츠
* 광고
    * 광고가 웹에서 자주 쓰이는데 왜 ad라는 요소는 없나요?
    * 그러면 모두가 $("ad").css("display", "none");
    * adblock이 어떻게 동작하는 지
    * $(".ad").css("display", "none")
    * $(".advertise").css("display", "none")
    * $(".ed").css("display", "none")
```
<section>
    <h1>부대찌개 레시피</h1>
</section>
<aside>
    <h1>연관 레시피</h1>
</aside>
```

### nav
* 네비게이션
```
    <nav class="gnb">
        <a href="#">후라이드</a>
        <a href="#">양념</a>
        <a href="#">오븐</a>
        <a href="#">사이드</a>
    </nav>
```
```
    <nav>
        <ol>
            <li><a href="#recipe-1">닭을 삶습니다</a></li>
            <li><a href="#recipe-2">닭을 삶습니다</a></li>
            <li><a href="#recipe-3">닭을 삶습니다</a></li>
        </ol>
    </nav>
    <section id="recipe-1">
        <h1>닭을 삶습니다</h1>
    </section>
    <section id="recipe-2">
        <h1>닭을 삶습니다</h1>
    </section>
    <section id="recipe-3">
        <h1>닭을 삶습니다</h1>
    </section>
```

### header
* 섹션의 시작영역
### footer
* 섹션의 마지막영역
```
<section>
    <header>
        <h1>배달의민족</h1>
    </header>
    실제내용들
    <footer>
        <p>copyright all right reserved @choeun</p>
    </footer>
</sectuon>
```

## Forms (주말)

# CSS (1 hour 30 min)
## CSS Layout
* layout (배치)
* 배치한다.
* 쌓이는 구조.
    * 특정한 것을 특정한 위치에 두는 것 (배치, 레이아웃)
    * Normal Flow
* 위에서부터 흐르는 구조
    * 콘텐츠가 시작부터 끝까지 흐르는
    * 레이아웃을 만든다 => 흐름을 바꾸는 것
    * 레이아웃을 생성 => reflow
* block formatting context
    * 아래로 쌓이는 구조 (블록이)
    * vertically
    * width, height 다 내가 원하는대로
    * <div>, <section>, <article>
* inline formatting context
    * 텍스트처럼 취급되는 것이 쌓이는 구조 (한줄로)
    * horizental
    * 가로 길이를 콘텐츠의 길이 (width)
    * 높이를 행간만큼 (line-height)
    * <span>, <storng>

* float
    * 이미지의 오른쪽이나 왼쪽에 텍스트를 노출시키기 위해 사용
    * float? (부유)
    * 특정 요소에 float를 넣으면 해당 요소를 부유하게 만듦
    * 부모요소가 float된 자식의 높이를, 자식을 인식하지 못해요.
    * float : left
    * float : right
    * 문제점
    * 1. 유동형 레이아웃과 고정형 레이아웃이 결합되면 UI가 깨지기 쉽다.
    * 2. 만약 0.1px이라도 계산을 잘못하면 레이아웃 깨짐

* clear
    * float된 요소의 다음 요소에 사용을 하며,
    * float를 해체해주기 위해서 사용
    * clear: left
    * clear: right
    * clear: both;

* box model
    * 모든 HTML 요소는 사각형 (box)
    * 가로 사이즈 (width)
    * 높이 (height)
    * 외곽선 (border)
    * 외곽선과 콘텐츠 사이 여백 (padding)
    * 박스와 박스 사이 여백 (margin)
    * 더하는 구조

 --------
|        |
|        |
 --------
```
.box {
    width: 150px;
    height: 150px;
    padding: 25px;
    border: 1px solid #000;
    margin: 25px;
}
```

* width
* height
* border
    * border: 1px solid #000000;
    * border: <border-width> <border-style> <border-color>
    * border-width:1px 2px 3px 4px;
    * border-style: solid;
    * border-color: #000000;
* padding
    * 시계방향으로 속성값을 작성
    * padding: <padding-top> <padding-right> <padding-bottom> <padding-left>
    * padding: 15px 10px 5px 0;
    * padding: 15px 0 10px;
    * padding: 15px 5px;
    * padding: 15px;
* margin
    * 만약 margin을 가진 요소
    * 두 요소가 서로 vertical 관계라면
    * margin은 병합됨
    * 부모 - 자식 관계에서는 부모가 border도 없고 padding도 없는 경우
    * float된 요소에서는 발생하지 X
    * collasping margin
    * 둘 중 큰 값을 따라감
* 계산하기 어려움
    * box-sizing
    * box 사이즈를 width나 height를 최댓값으로 두고
    * 나머지를 뺴는걸로
    * 나머지
    * box-sizing: content-box (나머지: X) (원래 상태)
    * box-sizing: border-box (나머지: padding, border)

* flexbox (이번 주 토요일)
    
## CSS Position (토요일)
## CSS Values & Units (토요일)

# 웹 퍼블리셔 vs 프론트엔드 개발자
* Front-End Engineering
    * UI / UX
        * 웹 퍼블리셔 / HTML, CSS, 접근성 할 줄 아는 사람
        * HTML & CSS & JavaScript(Interaction) 
        * 버튼을 어느 크기로 만들어야 유저가 편히 쓸까 (Design, Engineer)
        * 스와이프 애니메이션을 넣는데 가속도를 어떻게 넣을까? (Design, Engineer)
    * Web Application
        * JavaScript Only / HTML / CSS
        * Angular, React, Backbone
        * API와 UI를 매칭
        * 적절한 시점에 적절한 UI를 보이게
        * <?=DATA?>

---

내 메모

170530 HTML/CSS 조은

section은 특정 관심사의 유효범위 구획(시멘틱상 그룹핑)

div는 css 그룹핑용
검색엔진이나 스크린리더는 section을 우선한다

section

- 반드시 제목이 있어야만 한다(h1~h6)
- 브라우저는 h1가 두 개 나오면 나머지 하나를 자동적으로 h2로 레벨 다운시킨다(아웃라인 알고리즘), CSS를 적용받는 것은 동일, h1~h6을 구분해서 쓸 필요가 없음, 단 구버전 브라우저는 아웃라인 알고리즘을 지원하지 않음(IE), 모바일에서는 사용해도 되어요
- 첫 번째 h1은 서비스명으로 많이 쓰임

Section VS Div : 아웃라인 알고리즘 생성 유무

Section VS Article : 의존성 여부, 구분하기 모호함, 사파리의 읽기 도구는 article 기준으로 동작

class name에 ad라고 주게 되면 adblock에 막힐 가능성이 급증, 광고일수록 class명을 복잡하게 주세요

css class selector는 유니코드를 기반으로 동작하기에 전세계 언어를 지원(IE 제외)

gnb 글로벌 네비게이션 바

```html
<a href="#recipe-1"></a>
```

위 코드를 통해 페이지 내 이동 가능 (Indexing link)

line-height는 1.2정도 주어야 라인이 알맞음
img에서 alt가 y등의 긴 영어 문자열을 기준으로 되어있어서 약간의 아래 틈이 발생하는데, vertical-align: top을 적용하면 사라진다


무엇을 공부할 때는 그게 무엇인지를 명확히 아는 것이 중요하다

reflow : flow를 다시 계산하는 행위

block이 inline보다 훨씬 많이 쓰여요, 또한 block은 width height를 원하는만큼 지정가능해요

```html
<body>
  <header>
  <main>
  <footer>
</body>
```

레이아웃을 짤 때, 여러분들은 컨테이너를 잘 못 만들어요
비주얼에 너무 속지 마세요

HTML 기반 위에 CSS를 얹는 것이기에 HTML이 매우 중요해요

바뀔 여지가 있는 것은 레이아웃을 위한 div로 감싸주는 것이 좋아요

이 안에 있는 콘텐츠가 얼마든지 바뀔 수 있다, 콘텐츠와 상관없이 레이아웃이 짜여져야 한다 라는 것을 기준으로 만들어야 함

모듈 네이밍 : 그 레이아웃 요소를 왜 쓰는지에 초점 => 코드를 범용적으로 쓸 수 있는 관점

dsc : discription

입력란하고 보여주기란 모두 빼놓지 말고 작성해보아요

범용성과 변동성은 반비례 관계이니 어떤 쪽에 해당할지 고민해볼 것

이 둘은 비주얼상을 떠나 의미상으로 항상 붙어있는가?에 따라 마크업이 달라져요

button 태그는 자바스크립트로 동작하는 버튼이 필요할 때 만들어요

UI가 같다면 최대한 많이 재활용을 해보세요

float는 왼쪽이나 오른쪽에 무엇이든 올 수 있게 해줘요

웹은 2차원이 아니라 Z축이 존재하는 3차원이에요
float는 바닥 레이어보다 띄워져있어요
있다는 것은 알지만 밑에 애들이 제어할 수는 없어요
부모 요소가 비행자식요소를 찾지 못해요
(비행자식요소가 얼만큼의 height를 가지고 있는지 몰라요)

float는 flow를 변경하기는 하지만, normal-flow에 속하기 때문에 flow를 해치지 않아요, overflow를 적용했을 때 인지하도록 되는 것

float는 overflow의 처리대상이 아니기 때문에 잡아준 것이다!

html상으로는 아무 의미는 없는데 요소가 필요할 때, .row:after 또는 .row:before 를 사용

height를 고정값으로 주는 것은 유동적이지 않음
overflow hidden은 그 위에 레이어를 못 띄워요(페이스북에서 지구본을 클릭하면 별도 레이어로 나와야 하는데, overflow: hidden이 적용된 구간은 레이어가 나오지 않을거에요)
clear를 사용하려고 할 때 :after는 IE8부터 지원해요
이 밑으로 지원해야 하면 div.clear를 만들어서 넣어줘야 함

float의 결정적 단점(연약한 친구)

- 애초에 모바일이 고려되지 않은 친구
- 유동형 레이아웃과 고정형(pixel) 레이아웃이 결합되면 UI가 깨지기 쉽다
- 1px이라도 계산이 잘못되면 UI 깨짐

calc는 IE에서 아예 지원 안 함
box-sizing은 border-box로 하면 IE8 이상 지원

인스타그램은 댓글 영역 때문에 float로 구현 불가능(유동형으로 사이즈가 변해야 하기 때문)

UI를 만들 때 머릿속으로 불가능하다고 떠오르는 것이 있다면, 무엇인가 모르고 있어서 그런거에요(인스타라는 결과물이 있다면 우리도 할 수 있어요)

float를 극복하기 위한 것이 flexbox

모던 웹사이트 디자인의 정석 추천

border의 구성요소: 굵기, 보더의 형태, 색상 (보더 역시 패딩, 마진처럼 2번 더해지겠죠?)

width와 height를 고정으로 주면 콘텐츠가 넘쳐나요
(overflow: hidden이면 짤리는 부분 안 보여주고, scroll이나 auto를 주면 스크롤로 보여줄 수 있음)
overflow-x or overflow-y도 있어요

콘텐츠가 들어가는 박스는 보통은 height를 거의 안 넣어요
콘텐츠의 길이에 의존해서 늘어나기 위해서-

사이간격을 넓히기 위해서 padding을 주어요

margin은 특이하게 서로 vertical한 관계를 가진 요소라면 margin이 병합되어요, 둘 중에 큰 쪽을 따라가요, 음수라면 그 값을 빼요

부모-자식 관계에서 부모에 border와 padding이 없으면 margin이 병합되어요(0.1px이라도 들어가있으면 collapsing margin이 발생하지 않아요)
에러가 나는 것처럼 보여지는 대표적인 경우에요
float된 요소에서는 발생하지 않아요
둘 중 큰 값을 따라가요

box-sizing은 margin이 먹히지 않아요

vertical보다 horizental이 margin 계산하기 더 어려워요

box-sizing은 가로로 나열된 margin 계산과 유동형 레이아웃일 때 좋다

다양한 UI들 연습을 많이 해봐야 늘어요

float, flexbox 모두 잘 알아야 해요

유튜브 amp 채널 만들어보세요

border 설정을 잘못하면 hover 밑줄이 딸깍 거려보여요

프린트를 해서 레이아웃을 나눠서 생각해보면 쉬워요
무엇을 먼저 시작해볼지 고민해보세요-

https://www.youtube.com/channel/UCXPBsjgKKG2HqsKBhWA4uQw

시크릿모드

유튜브는 새로 고침이 발생하지 않아요
