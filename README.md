# Vue.js_note - vue 관련 메모

### 🟧 v-if & v-show
렌더링이 자주일어날 때; CSS 기반 토글만으로 초기 조건에 관계 없이 엘리먼트가 항상 렌더링
일반적으로 v-if는 토글 비용이 높고 v-show는 초기 렌더링 비용이 더 높습니다. 매우 자주 바꾸기를 원한다면 v-show를, 런타임 시 조건이 바뀌지 않으면 v-if를 권장합니다.

### 🟧 v-for & v-if
동일한 노드에 두가지 모두 있다면, v-for가 v-if보다 높은 우선순위를 갖습니다. 즉, v-if는 루프가 반복될 때마다 실행됩니다. 이는 일부 항목만 렌더링 하려는 경우 유용합니다.

### 🟧 $event로 DOM접근
때로 인라인 명령문 핸들러에서 원본 DOM 이벤트에 액세스 해야할 수도 있습니다. 특별한 $event 변수를 사용해 메소드에 전달할 수도 있습니다.

### 🟧 camelCase vs. kebab-case
HTML 속성은 대소 문자를 구분하지 않으므로 문자열이 아닌 템플릿을 사용할 때 camelCased prop 이름에 해당하는 kebab-case(하이픈 구분)를 사용해야 합니다.
```
props: ['myMessage'], <child my-message="안녕하세요!"></child>
```

### 🟧 폼입력 데이터 바인딩
텍스트 영역의 보간 `(<textarea>{{ text }}</textarea>)`은 작동하지 않습니다. 대신 v-model를 사용하십시오.
v-model 표현식의 초기 값이 어떤 옵션에도 없으면, <select> 엘리먼트는 “선택없음” 상태로 렌더링됩니다. iOS에서는 이 경우 변경 이벤트가 발생하지 않아 사용자가 첫 번째 항목을 선택할 수 없게됩니다. 사용하지 않는 옵션에 빈 값을 넣는 것이 좋습니다.
