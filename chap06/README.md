# 06. 표현이 자유로운 CSS3

## 06-1. CSS3를 공부하기 전에

### CSS3(Cascading Style Sheet)란?
CSS3 역시 아직까지 표진이 정해져 있지 않지만 이미 많은 브라우저에서 CSS3의 주요 속성들을 원지하고 있습니다.
CSS3는 CSS2나 CSS1에 비해 더욱 정교하고 화려한 화면을 구성할 수 있고, 애니메이션까지 지원한다는 것이 특징입니다.

### 브라우저마다 다르게 구현되는 CSS 프로퍼티
아직 브라우저들이 CSS3의 프로퍼티를 부분적으로만 구현하기 때문에 대부분의 CSS3 프로퍼티는 접두사를 붙여서 사용해야 합니다.
모든 브라우저에서 똑같은 결과를 만들어내려면 지금으로서는 최선의 방법입니다. CSS3 최종 규약이 완성되면 더이상 사용하진 않겠지만요.

| -webkit- | 웹킷 방식 프라우저(사파리, 크롬 등) |
| --- | --- |
| -moz- | 개코 방식 브라우저(모질라, 파이어폭스 등) |
| -o- | 오페라 브라우저 |
| -ms- | 인터넷 익스플로러 |

```css
-webkit-border-radius: 10px;
-moz-border-radius: 10px;
```

## 06-9. 새로운 CSS3 셀렉터

### 속성과 관련된 셀렉터
| 항목[속성^="값"] | "값"으로 시작하는 속성이 있는 항목 선택 |
| --- | --- |
| 항목[속성$="값"] | "값"으로 끝나는 속성이 있는 항목 선택 |
| 항목[속성*="값"] | "값"이 포함되는 속성이 있는 항목 선택 |

```css
a[href$="pdf"] {
    ...
}
```

### 슈도 클래스 :not과 :target
:not은 지정한 항목을 제외한 모든 항목을 선택합니다. 예를 들어 `*:not(a)`는 링크를 제외한 모든 항목을 선택합니다.
:target은 앵커를 이용해 페이지 내에서 점프를 할 때 타겟이 되는 부분을 선택합니다.

### 구조적 슈도 클래스
구조적 슈도 클래스는 여러 개가 나열된 것들 중에서 특정한 부분을 고르는 셀렉터입니다.

| :nth-child(n) | n번째 자식 선택 |
| --- | --- |
| :nth-last-child(n) | 끝에서부터 n번째 자식 선택 |
| :nth-of-type(n) | 타입이 같은 n번째 항목 선택 |
| :nth-last-of-type(n) | 끝에서부터 타입이 같은 n번째 항목 선택 |

## 06-11. 독특한 나만의 글자
CSS3를 이용하면 웹 페이지에 글꼴을 포함시킬 수 있기 때문에 사용자 시스템에 설치된 글꼴 뿐만아니라 훨씬 다양한 글꼴을 사용할 수 있습니다.

### 웹 페이지와 글꼴
@font-face는 이전부터 존재했지만, CSS3에 와서 표준으로 만들려고 하고 있기 때문에 함께 설명합니다.
이전에는 사용자 컴퓨터에 설치되어 있는 글꼴에 한해서만 화면에 정확하게 표시되고, 그 외의 글꼴은 브라우저 기본 글꼴로 표시 되었습니다. 하지만 CSS3에서는 글꼴을 서버에 함께 올리기만 하면 그 글꼴을 사용해 누구나 똑같이 볼 수 있는 페이지를 만들 수 있습니다.

### 글꼴 정의하기 및 사용하기
@font-face 속성을 이용해 글꼴을 정의할 수 있습니다.

```css
@font-face {
    font-family: 글꼴 이름;
    src: url(글꼴 파일 경로) format(파일 유형);
}
```

화면에 표시할 수 있는 파일 형식은 *truetype(ttf)* 와 *opentype(otf)*, *embedded-opentype(eot)*, *scalable-vector-graphic(svg, svgz)* 등이 있습니다.

```css
@font-face {
    font-family: Blackout;
    src: url("Blackout.ttf") format("truetype");
}

.text1 {
    font-family: Blackout;
}
```

### 기억해 두어야 할 사항
1. 글꼴의 라이센스를 확인해야 합니다.
2. 모든 브라우저가 @font-face를 지원하는 것은 아닙니다.
  - @font-face 속성을 지원하지 않는 브라우저를 생각하여 두 번째, 세 번째 글꼴도 함께 지정해두어야 합니다. (`font-family: Blackout, Arial Black;`)
3. 페이지 로딩 속도를 고려해야 합니다.
  - 너무 많은 @font-face는 글꼴 로딩에 많은 시간을 소모하게 합니다.
4. 설치된 글꼴인지 먼저 확인합니다.
  - @font-face로 정의한 글꼴일지라도 사용자 시스템에 이미 설치돼 있다면 로딩할 필요가 없습니다. 따라서 사용자 시스템에 설치되어 있는지를 먼저 확인해야 합니다.

```css
@font-face {
    font-family: Blackout, Arial Black;
    src: local("Blackout"), url("Blackout_2am.ttf") format("truetype");
}
```

5. IE는 eot 파일만 지원합니다.
  - IE는 eot만 지원하므로 모든 브라우저에서 제대로 동작하는 페이지를 만들려면 IE를 위한 소스코드를 한 줄 추가해야 합니다.

```css
@font-face {
    font-family: Blackout, Arial Black;
    src: url("Blackout.eot"); /* IE를 위한 코드 */
    src: local("Blackout"), url("Blackout_2am.ttf") format("truetype");
}
```