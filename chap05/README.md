# 05. 웹 폼 만들기

## 05-1. HTML5에서 무엇이 바뀌었을까?

### `<input>`에 추가된 타입들
HTML4의 `<input>` 태그에서 사용할 수 있었던 타입은 다음과 같습니다.

| type | 설명 | 
| --- | --- |
| text | 텍스트 |
| password | 패스워드 |
| checkbox | 체크 박스
| radio | 그룹 중에서 한 가지만 선택 가능 |
| file | 파일 업로드 |
| submit | 폼에 입력한 정보를 전송 |

HTML5에서는 아래의 타입이 더 추가되었습니다.

| type | 설명 |
| --- | --- |
| email | 이메일 주소 입력 |
| url | url 입력 |
| number | 상/하 버튼을 눌러 숫자 선택 |
| range | 슬라이드 막대로 지정된 범위의 숫자 선택 |
| date, datetime | 달력에서 날짜를 선택하거나 스핀 박스에서 시간을 선택 |
| search | 검색 상자 삽입 |
| color | 색상 선택 |

## 05-2. 새로 생긴 `<input>` 태그의 유형들
위 표와 같음

## 05-3. `<input>` 태그의 새로운 속성들

### 자동 완성 기능 제어 - autocomplete
자동 완성 기능이란 웹 브라우저에서 사용자가 입력한 내용을 기억했다가 비슷한 내용을 입력할 경우 이전에 입력했던 내용을 힌트로 보여주는 것을 말합니다.

### 입력 필드에 커서 표시하기 - autofocus
페이지를 불러오자마자 입력 필드 안에 마우스 커서가 표시되면 바로 입력ㅎ랄 수 있어서 아주 편리합니다. HTML5에서는 autofocus 속성으로 쉽게 해결할 수 있습니다.

### 사용 가능한 값 제시하기 - list
사용자가 텍스트 필드에 내용을 입력할 때 몇 개의 입력 가능한 값들을 데이터 목록으로 보여줄 수 있습니다.

### 입력 값 제한 - min, max, maxLength, step
min, max 속성은 input 필드의 최소값과 최대값을 지정합니다. maxLength는 텍스트 필드에 최대로 입력할 수 있는 문자 길이를 나타냅니다.
step 속성은 특정 input 타입에서 허용된 범위 내의 숫자의 일정한 간격을 가리킵니다.

### 힌트 표시하기 - placeholder
placeholder는 `<input>` 태그의 필드 안에 적당한 힌트 내용을 표시하고 있다가 그 필드를 클릭하게 되면 사용자가 입력할 수 있도록 내용이 사라지는 것을 말합니다.

### 필수 입력 필드 체크 - required
required 속성을 사용하면 폼에 내용을 입력하고 submit 단추를 눌러 서버로 폼을 전송하기 전에 필수 필드에 내용들이 모두 채워졌는지를 검사하게 됩니다. 내용이 채워지지 않고는 전송할 수 없습니다.