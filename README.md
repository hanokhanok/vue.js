# Vue.js 정리

## vue.js 설치하기
```
npm install vue
```

## vue.js 디렉티브
* v-text: 텍스트를 인코딩하여 문자 그대로 보여줌
* v-html: 태그를 파싱하여 화면에 구현함
* v-bind: id, class, style 등의 html 속성값에 뷰 데이터 값을 연결할 때 사용
* v-if: 참, 거짓 여부에 따라 html태그를 화면에 표시하거나 표시하지 않음. true일 때 렌더링되고 false일 때 삭제됨 / v-else, v-else-if로 추가적인 조건을 생성 가능.
* v-for: 배열이나 객체의 반복에 사용. 데이터의 갯수만큼 html태그를 반복적으로 출력
* v-on: 이벤트 감지 및 처리
* v-show: v-if와 유사하지만 css의 display: none 속성을 이용하여 실제 태그는 남아있고 화면상에서만 보이지 않음. template문법에서 사용불가.
* v-model: 양방향 바인딩. form에서 주로 사용하는 속성으로 form에서 입력한 값을 뷰 인스턴스의 데이터와 즉시 동기화. 입력된 값을 서버에 보내거나 추가로직 수행
* v-once: 처음 한번만 렌더링을 수행. 데이터가 변경되어도 처음값만 보여줌.

## 약어
* v-bind :로 줄일 수 있음
* v-on: @로 줄여서 표현 가능

## 컴포넌트 통신
### props
* 부모에서 자식으로 데이터를 전달하기 위해 사용(상위 컴포넌트에서 하위 컴포넌트로)
### emit
* 자식이 부모에게 데이터를 전달하기 위해 이벤트를 발생시키는 것.
### event bus
* 서로 관련이 없는 독립적인 컴포넌트끼리 데이터를 주고 받을 수 있음.
* $emit-이벤트 트리거, $on-이벤트 감지


## vue.js 라이프사이클
* beforeCreate: Vue인스턴스가 초기화된 직후에 발생.
* created: Vue인스턴스가 생성되고 데이터관찰, 계산형 속성, 메서드, 감시의 설정이 끝나면 호출 됨. DOM에는 추가되지 않은 상태.
* beforeMount: DOM인 el 요소에 vue 인스턴스가 마운트 되기 전에 호출 됨
* mounted: DOM인 el 요소에 vue 인스턴스가 마운트 된 후에 호출 됨
* beforeUpdate: 가상 DOM이 생성되기 전에 데이터가 변경될 때 호출 됨
* updated: 데이터의 변경으로 인해 가상 DOM이 다시 렌더링된 후에 호출 됨. DOM에 종속성이 있는 계산은 이 단계에서 수행해야 함
* beforeDestroy: vue 인스턴스가 제거되기 전 호출됨
* destroyed: vue 인스턴스가 제거된 후 호출됨

## computed와 watch
* computed: 데이터 연산들을 정의하는 영역
* computed와 method 비교: computued 속성은 해당 속성이 종속된 대상이 변경될 때만 함수를 실행
* watch: vue instance의 특정 property가 변경될 때 실행할 콜백함수 설정. 상대적으로 시간이 오래 소모되는 비동기적 처리에 적합함