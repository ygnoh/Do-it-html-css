# 02 HTML5로 기본적인 문서 만들기

## 02-1 HTML5의 문서 구조

### HTML4의 문서 구조 vs HTML5의 문서 구조
HTML5에서 가장 두드러지는 특징 중의 하나는 시맨틱 태그입니다.
HTML4에서는 웹 문서의 레이아웃을 구성할 때 `<div>` 태그를 이용해 텍스트나 이미지를 담아놓고, CSS를 사용해서 각 `<div>`를 원하는 형태로 배치하였습니다. `<div>` 태그는 아무 의미가 없고 그 안에 들어있는 내용들이 제작자가 붙이는 id에 따라 구분되는데, 이는 제작자가 임의로 붙이는 것이기 때문에 소스만 보아서는 문서 구조나 내용을 알기가 어렵습니다.

### 시맨틱 요소가 포함된 HTML5의 문서 구조
HTML5에서는 태그만 보고도 문서를 쉽게 이해할 수 있도록 의미를 가지는 태그들을 도입했는데 이를 시맨틱 요소(Semantic Element) 또는 시맨틱 태그라고 합니다.

| header | 사이트에 대한 소개 정보나 메인 메뉴, 사이트 로고 등 |
| --- | --- |
| nav | 메뉴나 링크 같은 네비게이션 요소들 |
| section | 실제 문서 내용. 또 다른 section을 포함할 수도 있음 |
| article | 문서 내용이 많을 경우 여러 개의 article로 나눌 수 있음 |
| aside | 주요 내용 외의 내용들을 넣어 문서의 주영역 주변에 배치 |
| footer | 작성자 정보나 저작권 정보, 관련 문서 링크 등 부가 정보 |

이렇게 소스만으로도 문서 내용을 알 수 있게 되면 검색 엔진에서 필요한 부분만 쉽게 찾아서 검색할 수 있습니다.

### HTML5의 문서 유형 지정 - DOCTYPE
DOCTYPE은 이 웹 페이지가 어떤 유형으로 만들어졌는지 정의하는 요소입니다. DOCTYPE을 선언해 놓지 않으면 브라우저별로 결과가 다르게 보일 수 있습니다.
DOCTYPE은 HTML 태그가 아닙니다. 따라서 웹 문서의 갖아 첫번째 줄, 즉 `<html>` 태그보다 먼저 와야 합니다. HTML5에서의 DOCTYPE은 아주 간단합니다: `<!DOCTYPE html>`

## 02-2 HTML5의 시맨틱 태그들

### 머리말 부분 지정 - `<header>` 태그
`<header>` 태그는 사이트 전체의 머리말이 될 수도 있고, 블로그 포스트의 머리말이 될 수도 있습니다.
사이트 전체의 머리말일 경우 주로 사이트 상단이나 왼쪽에 배치합니다.
본문에 사용된 `<header>`일 경우엔 본문의 머리말이기 때문에 `<h1>`에서 `<h6>`까지의 태그를 사용해 제목과 부제목을 표시하는 경우가 많습니다.

### 제목과 부제목의 묶음 - `<hgroup>` 태그
`<hgroup>` 태그는 제목과 그와 관련된 부제목을 묶어주는 것입니다. 제목과 부제목을 `<hgroup>`으로 묶게 되면 문서에서 중요한 뼈대가 어떤 것인지를 쉽게 알 수 있고 그만큼 문서를 빠르고 정확하게 조직할 수 있습니다.

### 내비게이션 링크 표현 - `<nav>` 태그
`<nav>` 태그는 문서 안에서, 혹은 다른 문서로 링크하기 위한 내비게이션 링크를 표현합니다. `<nav>` 태그는 `<header>`나 `<footer>` 또는 `<aside>` 태그 안에 포함시킬 수도 있고 독립하여 사용할 수도 있습니다. 즉, 위치에 영향을 받지 않습니다.

### 웹상의 실제 내용 - `<article>` 태그
신문기사가 여기저기에 인용될 수 있는 것처럼 `<article>` 태그를 사용한 컨텐츠는 웹에서 다른 곳으로 배포되거나 재사용될 수 있습니다. 보통 블로그의 포스트나 웹 사이트의 내용, 사용자가 등록한 코멘트, 웹 컨텐츠의 독립적인 항목 등이 모두 여기에 해당될 수 있습니다. 웹 컨텐츠를 자동 검색하는 로봇에서는 `<article>` 태그가 사용된 컨텐츠를 발견하면 배포 가능한 콘텐츠라는 것을 쉽게 알아낼 수 있게 됩니다.

### 컨텐츠를 그룹으로 묶어주는 - `<section>` 태그
HTML5에서도 제목을 붙여서 컨텐츠 그룹을 묶는 것을 `<section>` 태그라고 합니다. 시작 페이지라면 '사이트 소개'나 '뉴스', '연락 정보' 등의 섹션으로 나눌 수도 있고, 여러 탭으로 이루어진 뉴스 페이지라면 하나의 탭을 하나의 섹션으로 할 수도 있습니다.
하지만 단순히 컨텐츠를 묶기 위해 `<section>` 태그를 사용하는 것은 바람직하지 않습니다. 스타일을 적용하거나 스크립트를 적용하기 위해 컨텐츠 중 일부를 묶고 싶다면 `<div>` 태그를 사용하면 됩니다.
`<section>` 태그로 절을 나눈 후 그 안에 `<article>` 태그를 넣거나 또 다른 `<section>` 태그를 넣을 수도 있습니다.

### 본문을 표시하고 남는 내용 - `<aside>` 태그
블로그를 이용하다 보면 실제 블로그 포스트를 표시하는 부분 외에 왼쪽이나 오른쪽에 기타 내용들이 표시되는 부분이 있습니다. 흔히 '사이드 바'라고 부르는 이런 부분을 표시하는 요소가 `<aside>` 태그입니다.

### 제작자 정보나 저작권 정보 - `<footer>` 태그
`<footer>` 태그는 그 안에 다른 어떤 요소도 포함할 수 있습니다.