# Program Engineer Training

# Research Reports

## Overview

주어진 문제를 리서치하여 보고서를 작성합니다.

### How to do work

1. 문제를 읽어봅니다.
2. 문제의 핵심을 파악하고 웹 또는 그 외의 모든 루트를 사용해서 리서치를 합니다.
3. 보고서는 Mark Down 형식으로 작성합니다.
4. 작성한 md 파일을 branch 하여 PR(pull request) 를 보냅니다.

## Reports

1. `package.json` 에 대해 작성하세요.
2. RDB 와 NoSQL 을 비교하여 작성하세요.
3. Javascript Prototype 에 대해 작성하세요.

# Javascript Training

## Overview

주어진 조건에서 코드를 작성합니다.

### How to do work

1. 요구사항에 맞게 HTML, CSS, JS를 생성합니다.
2. 구현이 끝난 branch를 PR(pull request). PR은 최종본 하나만 보냅니다.
3. PR 코멘트에 내용을 작성합니다.

### Requirements:

1. 외부 JS 프레임웍, 라이브러리, CSS, 마크업 컴포넌트 등을 사용하지 않습니다.
2. vanilla js, ECMAScript 2015(ES6)을 사용합니다.
3. HTML 마크업의 body 에는 `//div[@id='root']`인 DOM 하나만 추가하고 모든 DOM은 JS로 동적 제어합니다.

## Works

### (work.1) localStorage 를 사용한 todo 리스트 작성

1. 인풋박스를 통해 텍스트 입력과 엔터키와 버튼으로 작성 완료를 합니다.
2. 입력된 텍스트는 목록으로 보여지며 localStorage 에 저장됩니다.
3. 작성된 todo 아이템을 클릭하면 localStorage 에 삭제됩니다.
4. 작성과 삭제는 동적 화면으로 페이지 새로고침 없이 구현되야 합니다.

### (work.2) fetch 를 이용해서 API 호출 하기

1. fetch 함수를 이용해서 웹상의 json 을 호출합니다.
2. 호출 주소는 다음과 같습니다. http://dummy.restapiexample.com/api/v1/employees
3. 가져온 데이터는 table 의 header, body 를 이용해서 정돈하여 보여줍니다.
4. 버튼을 클릭하여 페이지의 새로고침 없이 데이터를 새로고침 해야합니다.

### (work.3) Date 의 prototype 을 확장하여 시계 만들기

1. Date 의 prototype 을 확장한 새로훈 함수를 작성합니다.
2. 시간은 초 단위까지 표시하며 동적으로 변화하는 시계를 구현합니다.
3. 버튼을 클릭해서 시간 표시와 타이머 스위칭하여 보여줄수 있어야합니다.
4. 타이버는 ms 단위로 보여지며 스톱 기능과 랩타임 기능을 구현합니다.
