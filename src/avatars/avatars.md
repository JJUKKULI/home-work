# 안녕하시렵니까?

뭔가 부트캠프로 거의 집에 일심동체되어 하루를 살다보니
맑은 날씨의 이끌려 점심시간에 잠시 외식을 하려 나갔는데요....
👍🏻 음, 역시 집이 최곱니다! (너무 추워..🤧)

HTML form의 여러 tag부터 Git Compilot을 쓰며 script맛보기까지 공부하고 Css도 맛보기정도만 학습해보았습니다.

그러면 회고 시작하겠습니당 🚀🚀

# Form-input

```
<form action="http://formspree.io/f/xeqwwbwk" method="post">
      <fieldset>
        <legend>폼 서식</legend>
        <div>
          <label for="userName">이름</label>
          <input
            type="text"
            name="userName"
            id="userName"
            required
            placeholder="이름을 입력해주세요"
            maxlength="5"
            minlength="3"
          />
          <!-- 위에 input id를 label for에 넣음으로서 스크린리더가 userName을 인식 -->
        </div>
        <div>
          <label for="userPwd">비밀번호</label>
          <input
            type="password"
            name="userPwd"
            id="userPwd"
            required
            placeholder="8자리 이상 기입"
          />
        </div>
        <!-- 검색입력서식 -->
        <div>
          <label for="likelionSearch">검색</label>
          <input type="search" name="likelionSearch" id="likelionSearch" />
          <!-- html5에 새롭게 추가된 타입 search -->
        </div>
        <!-- 이메일입력서식 -->
        <div>
          <label for="userEmail">이메일</label>
          <input type="email" name="userEmail" id="userEmail" required />
        </div>
        <!-- 연락처입력서식 -->
        <div>
          <label for="userPhone">연락처</label>
          <input type="tel" name="userPhone" id="userPhone" required />
        </div>
        <!-- 체크박스입력서식 -->
        <div>
          <input
            type="checkbox"
            value="html"
            name="classLikelion"
            id="classHtml"
          />
          <label for="classHtml">HTML</label>
        </div>
        <div>
          <input
            type="checkbox"
            value="css"
            name="classLikelion"
            id="classCss"
          />
          <label for="classCss">CSS</label>
        </div>
        <div>
          <input type="checkbox" value="js" name="classLikelion" id="classJs" />
          <label for="classJs">JS</label>
        </div>
        <!-- 라디오 -->
        <div>
          <input type="radio" name="classRoom" id="classRoom1" />
          <label for="classRoom1">회고 1팀</label>
        </div>
        <div>
          <input type="radio" name="classRoom" id="classRoom2" />
          <label for="classRoom2">회고 2팀</label>
        </div>
        <!-- 전송 버튼 -->
        <input type="submit" value="전송" />
      </fieldset>
    </form>
```

---

## 📌 코드 분석

```html
<form action="http://formspree.io/f/xeqwwbwk" method="post"></form>
```

- `action`: 사용자가 입력한 데이터를 전송할 URL (`formspree.io`를 사용해서 테스트 가능)
- `method="post"`: 데이터를 숨겨서 전송하는 방식 (보안에 유리)

---

### **입력 필드 (input 요소)**

```html
<label for="userName">이름</label>
<input
  type="text"
  name="userName"
  id="userName"
  required
  placeholder="이름을 입력해주세요"
  maxlength="5"
  minlength="3"
/>
```

- `type="text"`: 한 줄짜리 텍스트 입력
- `name="userName"`: 서버에서 받을 변수명
- `id="userName"`: `<label>`과 연결
- `required`: 필수 입력
- `placeholder="이름을 입력해주세요"`: 안내 문구
- `maxlength="5"` & `minlength="3"`: 입력 가능한 글자수 제한

---

### **비밀번호 입력**

```html
<label for="userPwd">비밀번호</label>
<input
  type="password"
  name="userPwd"
  id="userPwd"
  required
  placeholder="8자리 이상 기입"
/>
```

- `type="password"`: 입력값이 가려짐
- `required`: 필수 입력
- `placeholder`: 비밀번호 길이 안내 (하지만 `minlength="8"`을 추가하면 더 좋음!)

---

### **검색 입력**

```html
<label for="likelionSearch">검색</label>
<input type="search" name="likelionSearch" id="likelionSearch" />
```

- `type="search"`: 검색창 (브라우저에서 X버튼 제공)

---

### **이메일 & 전화번호 입력**

```html
<label for="userEmail">이메일</label>
<input type="email" name="userEmail" id="userEmail" required />

<label for="userPhone">연락처</label>
<input type="tel" name="userPhone" id="userPhone" required />
```

- `type="email"`: 이메일 형식 체크
- `type="tel"`: 전화번호 입력 (하지만 `pattern` 추가하면 더 정확한 형식 강제 가능)

---

### **체크박스 (다중 선택)**

```html
<input type="checkbox" value="html" name="classLikelion" id="classHtml" />
<label for="classHtml">HTML</label>

<input type="checkbox" value="css" name="classLikelion" id="classCss" />
<label for="classCss">CSS</label>

<input type="checkbox" value="js" name="classLikelion" id="classJs" />
<label for="classJs">JS</label>
```

- `type="checkbox"`: 여러 개 선택 가능
- 같은 `name="classLikelion"`으로 묶여서 서버에서 배열로 받음

---

### **라디오 버튼 (단일 선택)**

```html
<input type="radio" name="classRoom" id="classRoom1" />
<label for="classRoom1">회고 1팀</label>

<input type="radio" name="classRoom" id="classRoom2" />
<label for="classRoom2">회고 2팀</label>
```

- `type="radio"`: 하나만 선택 가능
- 같은 `name="classRoom"`을 사용해야 하나만 선택 가능
- **❗️`value` 속성이 없어서 서버에서 선택값을 받을 수 없음! 수정 필요!**

---

### **전송 버튼**

```html
<input type="submit" value="전송" />
```

- `type="submit"`: 폼 데이터를 전송하는 버튼(action에 기입한 주소)
- `value="전송"`: 버튼에 표시될 텍스트

---

# Form-button

```
    <form action="/" method="post" id="buttonForm">
      <div>
        <label for="user">사용자 이름</label
        ><input type="text" name="user" id="user" />
      </div>
      <div>
        <label for="pwd">사용자 암호</label
        ><input type="password" name="pwd" id="pwd" />
      </div>
      <div>
        <input type="submit" value="전송" />
        <input type="reset" value="초기화" />
        <input type="button" value="Clike Me!" />
      </div>
      <div>
        <button type="submit">전송</button>
        <button type="reset">초기화</button>
        <button type="button">클릭!</button>
      </div>
      <div>
        <button type="submit">
          <img src="/src/assets/icon/search.svg" alt="전송하기" />
        </button>
        <button type="submit" aria-label="전송해줘">
          <img src="/src/assets/icon/search.svg" alt="" />
        </button>
        <button type="submit" aria-label="검색해줘">
          <svg
            width="12"
            height="12"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              id="Union"
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M7.14574 8.55995C6.45201 8.99709 5.63054 9.25 4.75 9.25C2.26472 9.25 0.25 7.23528 0.25 4.75C0.25 2.26472 2.26472 0.25 4.75 0.25C7.23528 0.25 9.25 2.26472 9.25 4.75C9.25 5.63054 8.99709 6.45201 8.55995 7.14574L11.4571 10.0429C11.8476 10.4334 11.8476 11.0666 11.4571 11.4571C11.0666 11.8476 10.4334 11.8476 10.0429 11.4571L7.14574 8.55995ZM7.25 4.75C7.25 6.13071 6.13071 7.25 4.75 7.25C3.36929 7.25 2.25 6.13071 2.25 4.75C2.25 3.36929 3.36929 2.25 4.75 2.25C6.13071 2.25 7.25 3.36929 7.25 4.75Z"
              fill="#181818"
            />
          </svg>
        </button>
      </div>
    </form>
    <button type="reset" form="buttonForm">초기화</button>
    <!-- 위의 코드는 form바깥에 있으면 작동 X 하지만 id를 지정해주고 form을 버튼에 넣어주면 작동-->
```

## 📌 **코드 분석**

```html
<form action="/" method="post" id="buttonForm"></form>
```

- `action="/"`: 현재 페이지로 데이터를 전송
- `method="post"`: 데이터를 숨긴 상태로 전송
- `id="buttonForm"`: 특정 버튼이 이 폼을 참조할 수 있도록 ID 지정

---

### **입력 필드**

```html
<label for="user">사용자 이름</label>
<input type="text" name="user" id="user" />

<label for="pwd">사용자 암호</label>
<input type="password" name="pwd" id="pwd" />
```

- `type="text"`: 사용자 이름 입력
- `type="password"`: 비밀번호 입력 (입력값이 가려짐)

---

### **버튼 종류 비교**

```html
<input type="submit" value="전송" />
<input type="reset" value="초기화" />
<input type="button" value="Click Me!" />
```

- `type="submit"`: 폼 데이터를 전송
- `type="reset"`: 폼 입력 내용을 초기화
- `type="button"`: 기본 동작 없음 (JS 이벤트 핸들링 필요)

```html
<button type="submit">전송</button>
<button type="reset">초기화</button>
<button type="button">클릭!</button>
```

- `<button>` 태그를 사용하면 버튼 내부에 텍스트, 이미지 등 다양한 요소 포함 가능

---

### **아이콘 버튼 활용**

```html
<button type="submit">
  <img src="/src/assets/icon/search.svg" alt="전송하기" />
</button>
```

- `<img>` 버튼 내부에 넣어서 아이콘 버튼 구현
- `alt` 속성으로 접근성 향상

```html
<button type="submit" aria-label="전송해줘">
  <img src="/src/assets/icon/search.svg" alt="" />
</button>
```

- `aria-label`: `alt` 속성이 비어 있더라도 보조기기가 버튼 기능을 인식하도록 도움

```html
<button type="submit" aria-label="검색해줘">
  <svg>...</svg>
</button>
```

- `<svg>`를 직접 버튼에 포함하여 벡터 아이콘 사용

---

### **폼 외부 버튼이 폼을 조작하는 방법**

```html
<button type="reset" form="buttonForm">초기화</button>
```

- `form="buttonForm"`: 폼 바깥에 있어도 해당 폼을 조작 가능하도록 설정
- `type="reset"`: 폼 데이터를 초기화

⚠️ **주의:** 폼 바깥의 `<button>`은 `form` 속성을 지정하지 않으면 동작하지 않음!

---

# Form-select-textarea

```html
  <style>
      .sr-only {
        position: absolute;
        width: 1px;
        height: 1px;
        padding: 0;
        margin: -1px;
        overflow: hidden;
        clip: rect(0, 0, 0, 0);
        white-space: nowrap;
        border-width: 0;
      }
    </style>
  </head>
  <body>
    <h1>폼 (select, textarea)요소</h1>
    <h2>select 요소</h2>
    <form action="/" method="post">
      <div>
        <label for="petSelect">반려동물</label>
        <select name="petSelect" id="petSelect">
          <option value="">--반려동물 선택--</option>
          <option value="dog">강아지</option>
          <option value="cat">고양이</option>
          <option value="hamster">햄스터</option>
          <option value="spider">거미</option>
          <option value="goldenfish">금붕어</option>
          <option value="parrot">앵무새</option>
        </select>
      </div>
    </form>
    <h2>textarea 요소</h2>
    <form action="/" method="post"></form>
    <div>
      <label for="message"
        >내용
        <span aria-hidden="true"></span>
        <span class="sr-only"></span>
      </label>
      <textarea
        placeholder="메세지를 입력해주세요"
        name="message"
        id="message"
        cols="50"
        rows="20"
      ></textarea>
    </div>
  </body>
```

## 📌 **코드 분석**

```html
<style>
  .sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border-width: 0;
  }
</style>
```

- `.sr-only`: **스크린 리더 전용 스타일**  
  → 화면에는 보이지 않지만 보조 기기가 읽을 수 있도록 설정

---

## **`select` 요소 분석**

```html
<form action="/" method="post">
  <div>
    <label for="petSelect">반려동물</label>
    <select name="petSelect" id="petSelect">
      <option value="">--반려동물 선택--</option>
      <option value="dog">강아지</option>
      <option value="cat">고양이</option>
      <option value="hamster">햄스터</option>
      <option value="spider">거미</option>
      <option value="goldenfish">금붕어</option>
      <option value="parrot">앵무새</option>
    </select>
  </div>
</form>
```

✅ **좋은 점**  
✔️ `label`과 `for` 속성 연결 → 접근성 향상  
✔️ `option value` 사용 → 서버에서 값 처리 가능  
✔️ 기본적으로 `--반려동물 선택--` 옵션을 제공하여 선택 유도

⚠️ **개선하면 좋은 점**

- `<option value="">--반려동물 선택--</option>`은 `disabled selected` 속성을 추가하면 더 명확하게 동작
  ```html
  <option value="" disabled selected>--반려동물 선택--</option>
  ```

---

## **`textarea` 요소 분석**

```html
<form action="/" method="post"></form>
<div>
  <label for="message">
    내용
    <span aria-hidden="true"></span>
    <span class="sr-only"></span>
  </label>
  <textarea
    placeholder="메세지를 입력해주세요"
    name="message"
    id="message"
    cols="50"
    rows="20"
  ></textarea>
</div>
```

✅ **좋은 점**  
✔️ `label for="message"`로 접근성 강화  
✔️ `placeholder`를 추가하여 사용자 안내  
✔️ `cols="50" rows="20"`로 기본 크기 지정

⚠️ **개선하면 좋은 점**

- `<form>` 태그가 `textarea`를 감싸고 있지 않음 → `<form>`을 올바르게 배치해야 한다용!
  ```html
  <form action="/" method="post">
    <div>
      <label for="message">내용</label>
      <textarea
        placeholder="메세지를 입력해주세요"
        name="message"
        id="message"
        cols="50"
        rows="20"
      ></textarea>
    </div>
  </form>
  ```
- `<span aria-hidden="true"></span>`과 `<span class="sr-only"></span>`이 `label` 안에 있지만 역할 없음 → 삭제해도 무방

---

## 🔥 **총정리 (좋은 점 & 개선할 점)**

✅ **좋은 점**  
✔️ `label`과 `for` 속성을 활용한 접근성 강화  
✔️ `placeholder`로 사용자 가이드 제공  
✔️ `option` 값 활용하여 서버에서 선택값 처리 가능

🔧 **개선하면 좋은 점**  
1️⃣ `form` 태그가 `textarea`를 감싸지 않고 있음 → 올바르게 감싸기  
2️⃣ `<option>`의 첫 번째 항목에 `disabled selected` 추가하기  
3️⃣ 불필요한 `<span>` 태그 삭제하여 코드 정리

---

# dialog-popover

```html
    <style>
      dialog.panel-dialog::backdrop {
        background: linear-gradient(to bottom right, #ffdee9, #b5fffc);
      }
    </style>
    <script type="module">
      // DOM Selection
      const showDialogButton = document.querySelector('.show-dialog');
      const closeDialogButton = document.querySelector('.close-dialog');
      const panelDialog = document.querySelector('.panel-dialog');

      // Function Implementation
      const openDialog = () => {
        panelDialog.showModal();
      };

      const closeDialog = () => {
        panelDialog.close();
      };

      // Event Binding
      showDialogButton.addEventListener('click', openDialog);
      closeDialogButton.addEventListener('click', closeDialog);
    </script>
  </head>
  <body>
    <h1>dialog 요소</h1>
    <div class="dialog-area">
      <button type="button" class="show-dialog">모달창 보기</button>

      <dialog class="panel-dialog" aria-labelledby="event">
        <h2 id="event">깜짝 혜택</h2>
        <p>
          AI 코딩 도구를 활용하면 코드 생성 및 자동화, 개발 워크플로우와의 통합
          등이 가능하며 기존 개발 환경 대비 생산성을 높일 수 있습니다. 그러나
          개발자를 꿈꾸며 학습을하는 예비 개발자에게 AI 코딩 도구는 양날의 검이
          될 수 있습니다. AI 코딩 도구에만 의존하는 주니어 개발자는 경쟁력을
          갖출 수 없기 때문입니다. 오히려 더 깊이 있게 언어를 학습하고 좋은
          질문을 할 수 있도록 문해력(Literacy)을 기르는 것이 필요합니다. 다만 AI
          도구를 완전히 배제하는 것이 아닌 학습을 위한 파트너로서 활용할 것을
          추천합니다.
        </p>
        <button type="button" class="close-dialog">닫기</button>
      </dialog>
    </div>
    <h1>popover속성</h1>
    <button type="button" popovertarget="popovertarget" class="button-popover">
      팝오버 보기
    </button>
    <div popover id="popoverContent">
      <p>팝오버 내용</p>
    </div>
  </body>
```

## 📌 **코드 분석**

### `dialog` 요소 분석

```html
<style>
  dialog.panel-dialog::backdrop {
    background: linear-gradient(to bottom right, #ffdee9, #b5fffc);
  }
</style>
```

✅ **좋은 점**  
✔️ `::backdrop` 스타일을 적용하여 모달 배경을 화려하게 꾸밈  
✔️ `linear-gradient`를 사용해 부드러운 색상 전환 효과 적용

---

### `dialog` 관련 JS 기능 분석

```javascript
<script type="module">
  // DOM Selection
  const showDialogButton = document.querySelector('.show-dialog');
  const closeDialogButton = document.querySelector('.close-dialog');
  const panelDialog = document.querySelector('.panel-dialog');

  // Function Implementation
  const openDialog = () => {
    panelDialog.showModal();
  };

  const closeDialog = () => {
    panelDialog.close();
  };

  // Event Binding
  showDialogButton.addEventListener('click', openDialog);
  closeDialogButton.addEventListener('click', closeDialog);
</script>
```

✅ **좋은 점**  
✔️ `showModal()`과 `close()`를 활용하여 다이얼로그 창을 열고 닫는 기능 구현  
✔️ `addEventListener`를 활용한 이벤트 바인딩으로 버튼 클릭 시 동작하도록 설정

⚠️ **개선하면 좋은 점**

- 버튼이 `null`일 경우 에러 발생 가능 → `if (showDialogButton)` 체크 추가하기
  ```javascript
  if (showDialogButton && closeDialogButton && panelDialog) {
    showDialogButton.addEventListener("click", openDialog);
    closeDialogButton.addEventListener("click", closeDialog);
  }
  ```

---

### `dialog` HTML 분석

```html
<div class="dialog-area">
  <button type="button" class="show-dialog">모달창 보기</button>
  <dialog class="panel-dialog" aria-labelledby="event">
    <h2 id="event">깜짝 혜택</h2>
    <p>
      AI 코딩 도구를 활용하면 코드 생성 및 자동화, 개발 워크플로우와의 통합 등이
      가능하며...
    </p>
    <button type="button" class="close-dialog">닫기</button>
  </dialog>
</div>
```

✅ **좋은 점**  
✔️ `dialog` 태그 사용으로 기본 제공되는 모달 기능 활용  
✔️ `aria-labelledby`를 활용하여 접근성 향상  
✔️ `button`을 이용한 열기/닫기 기능 제공

⚠️ **개선하면 좋은 점**

- `dialog`가 `open` 속성이 없으므로 초기 렌더링 시 안 보이도록 확인 필요
  ```html
  <dialog class="panel-dialog" aria-labelledby="event" open></dialog>
  ```
  → **`open` 속성을 제거하고 JS로만 조작하는 것이 일반적**

---

### `popover` 요소 분석

```html
<h1>popover속성</h1>
<button type="button" popovertarget="popoverContent" class="button-popover">
  팝오버 보기
</button>
<div popover id="popoverContent">
  <p>팝오버 내용</p>
</div>
```

✅ **좋은 점**  
✔️ `popover` 속성을 활용한 팝오버 기능 사용  
✔️ `popovertarget` 속성을 통해 버튼 클릭 시 팝오버 표시 가능

⚠️ **개선하면 좋은 점**

- `popover` 속성은 브라우저 지원이 제한적이므로 **대체 방식(JS 이벤트 기반 토글)** 고려
  ```javascript
  document.querySelector(".button-popover").addEventListener("click", () => {
    const popover = document.getElementById("popoverContent");
    popover.togglePopover();
  });
  ```

---

## 🔥 **총정리 (좋은 점 & 개선할 점)**

✅ **좋은 점**  
✔️ `dialog`와 `popover`를 활용한 네이티브 UI 구현  
✔️ `aria-labelledby` 적용으로 접근성 향상  
✔️ `linear-gradient`를 이용한 시각적 효과 추가

🔧 **개선하면 좋은 점**  
1️⃣ `null` 체크 추가하여 JS 코드 안전성 강화  
2️⃣ `dialog`의 `open` 속성 제거 후 JS에서 조작  
3️⃣ `popover` 속성의 브라우저 지원 확인 후 JS 대체 방식 고려

---

# Details-summary

## ✅ `<details>` & `<summary>` 태그 정리

이 태그들은 사용자가 클릭하면 내용을 펼쳐볼 수 있도록 도와주는 HTML 요소

### 🔹 `<details>` 태그

- 접었다 펼 수 있는 콘텐츠 블록을 제작.
- 기본적으로 닫혀 있으며, 사용자가 클릭하면 열림

### 🔹 `<summary>` 태그

- `<details>` 태그 안에서 제목 역할
- 클릭하면 숨겨진 내용을 보여줌

### 🔹 코드 분석

```html
<details>
  <summary>국민 내일배움카드</summary>
  <!-- 클릭 가능한 제목 -->
  <figure>
    <img src="/src/assets/thumbnail/learn-card.png" alt="" />
    <!-- 이미지 -->
  </figure>
  <p>
    국민 스스로 직업능력개발훈련을 실시할 수 있도록 훈련비 등을 지원받을 수 있는
    카드
  </p>
</details>
```

- `summary`: 클릭하면 세부 내용을 열거나 닫을 수 있는 제목!
- `figure`: 이미지를 포함하는 블록 (시각적 요소 추가 가능!)
- `p`: 설명 내용을 담는 태그

### 🎯 활용 예시

- FAQ (자주 묻는 질문)
- 제품 상세 정보
- 기술 문서에서 코드 설명

---

# Script (feat. GitHub Compilot)

```html
    <link rel="stylesheet" href="/src/html/styles/23-script.css" />
    <script type="module" src="/src/html/js/23-script.js"></script>
  </head>
  <body>
    <h1>script 요소</h1>
    <button type="button" class="flip-button">카드 뒤집기</button>

    <div class="card-wrapper">
      <div class="card">
        <div class="card-face card-face-black"></div>
        <div class="card-face card-face-white"></div>
      </div>
    </div>
  </body>
```

## ✅ `<script>` 요소 정리

### 🔹 코드 구조

```html
<link rel="stylesheet" href="/src/html/styles/23-script.css" />
<script type="module" src="/src/html/js/23-script.js"></script>
```

1. **CSS 연결:** 스타일 파일을 불러와서 적용
2. **JS 연결:** `module` 타입으로 JavaScript 파일을 불러옴
   - `module`은 `import/export` 기능을 지원

### 🔹 주요 HTML 요소

```html
<button type="button" class="flip-button">카드 뒤집기</button>
```

- 클릭하면 카드가 뒤집힘

```html
<div class="card-wrapper">
  <div class="card">
    <div class="card-face card-face-black"></div>
    <div class="card-face card-face-white"></div>
  </div>
</div>
```

- `card-wrapper` 안에 `card`가 존재
- `card`는 앞면(`card-face-black`)과 뒷면(`card-face-white`)으로 구성됨

### 🔹 예상되는 JavaScript 동작

- `flip-button` 클릭 시 `.card`에 **CSS 클래스를 추가하여 회전 애니메이션 적용**
- `document.querySelector(".flip-button")`으로 버튼을 선택 후 `addEventListener("click", function() {...})`으로 이벤트 처리할 가능성이 높음!  
  (해당 css & js은 `learn-html-css/html/js or styles` 파일 참조)

---

## 🚀 GitHub Copilot 사용법 맛보기

### 🔹 확장 프로그램 설치

1. **Extensions**(확장 프로그램)에서 **GitHub Copilot** 설치

### 🔹 Copilot 추천 코드 적용

- 추천 코드가 나오면 **Tap** 키를 누르면 적용

### 🔹 Copilot 채팅 단축키

- **cmd + shift + i**

### 🔹 Copilot 작은 검색창

- **cmd + i**

---

# Css-basic

HTML

```html
    <!-- external style sheet -->
    <link rel="stylesheet" href="/src/css/styles/01-css-basic.css" />
    <style>
      h2 {
        font-size: 36px;
      }
    </style>
  </head>
  <body>
    <!-- Inline style sheet -->
    <h1 style="color: red">CSS 기초</h1>
    <h2>CSS 기본 문법</h2>
    <p>
      AI 코딩 도구를 활용하면 코드 생성 및 자동화, 개발 워크플로우와의 통합 등이
      가능하며 기존 개발 환경 대비 생산성을 높일 수 있습니다. 그러나 개발자를
      꿈꾸며 학습을하는 예비 개발자에게 AI 코딩 도구는 양날의 검이 될 수
      있습니다. AI 코딩 도구에만 의존하는 주니어 개발자는 경쟁력을 갖출 수 없기
      때문입니다. 오히려 더 깊이 있게 언어를 학습하고 좋은 질문을 할 수 있도록
      문해력(Literacy)을 기르는 것이 필요합니다. 다만 AI 도구를 완전히 배제하는
      것이 아닌 학습을 위한 파트너로서 활용할 것을 추천합니다.
    </p>
  </body>
```

---

## ✅ HTML 코드 분석

```html
<link rel="stylesheet" href="/src/css/styles/01-css-basic.css" />
```

- `rel="stylesheet"`: 이 속성은 연결되는 파일이 스타일시트(CSS)임을 알려줌
- `href="/src/css/styles/01-css-basic.css"`: `href` 속성은 연결할 CSS 파일의 경로를 지정. 이 경우 `/src/css/styles/01-css-basic.css` 경로에 있는 `01-css-basic.css` 파일을 연결

### 중요한 점:

- 경로(`/src/css/styles/01-css-basic.css`)가 HTML 파일과 맞는 위치에 있는지 확인
- 이 `<link>` 태그는 `<head>` 태그 안에 넣는 것이 일반적

---

CSS

```css
/* body 요소의 배경색상 지정 */
body {
  background-color: yellow;
  color: rgb(0 0 255/0.5);
  font-family: Arial, Helvetica, sans-serif;
}
```

---

## ✅CSS 코드 분석

### `color` (글자 색상)

- 글자의 색상을 지정하는 속성.
- 다양한 색상 표기법이 존재하지만, 주로 `rgba`(Red, Green, Blue, Alpha)나 `hsla`(Hue, Saturation, Lightness, Alpha)를 사용함.
  - `rgba(0, 0, 255, 0.5);` → 파란색(#0000FF) + 50% 투명도
  - `hsla(240, 100%, 50%, 0.5);` → 같은 색상 표현 가능

### `background-color` (배경색)

- 요소의 배경색을 설정하는 속성.
- 여기서는 yellow(노란색)으로 지정.

### `font-family `(글꼴 설정)

- 텍스트의 폰트를 지정하는 속성.
- 서체 계열:
  - `serif` → 획이 있는 글꼴 (ex: Times New Roman)
  - `sans-serif` → 획이 없는 깔끔한 글꼴 (ex: Arial, Helvetica)
- 현대적인 웹 환경에서는 모바일 가독성을 고려해 sans-serif 폰트를 주로 사용함.
- `font-family: Arial, Helvetica, sans-serif;`
  **→ 사용자의 시스템에 Arial이 있으면 적용, 없으면 Helvetica, 그것도 없으면 sans-serif 계열 폰트 적용.**

---

# 📌 CSS 수업 요점 메모

---

## CSS 선택자

### `a` 태그 속성 선택자

- `href^=https:` → `a` 태그 중 `href`가 `https:`로 시작하는 요소만 스타일 적용

### 상태 선택자

- `:visited` → 방문한 후 돌아왔을 때 변화
- `:hover` → 마우스를 올렸을 때 변화
- `:focus` → `tab` 등으로 포커싱 시 변화
- `:active` → 클릭 시 (`focus` + `active` 상태)

### 가상 선택자 vs 가상 요소

- `:pseudo-class` → 가상 클래스 (`:hover`, `:focus` 등)
- `::pseudo-element` → 가상 요소 (`::before`, `::after` 등)

## CSS 우선순위 (Specificity)

### 우선순위 계산

- 선택자 점수는 태그가 구체적일수록 높음
- `body h2 + p {}` → 구체적으로 지정할수록 우선 적용됨
- `body p[class] {}` → 점수 10점
- `.ai {}` → 점수 10점
- `id` 선택자 (`#id`) → 100점
- `!important` 사용 시 우선순위 규칙 무시 (사용 자제)

### 우선순위 정리 (높은 순서)

1. `!important`
2. 인라인 스타일 (`style=""`)
3. `id` 선택자 (`#id`)
4. 클래스 선택자 (`.class`), 속성 선택자 (`[attr]`)
5. 태그 선택자 (`div`, `p` 등)
6. 전체 선택자 (`*`)

### 클래스 중첩

- `<p class="copilot ai">` → 클래스 두 개 부여 가능
- `.ai.copilot {}` → 두 개의 클래스가 모두 있는 요소에만 적용 (점수 20점)

## 폰트 및 크기 단위

- `font` 속성에서 `px`과 폰트명은 필수
- `line-height`는 `font-size`가 없으면 부모 요소를 따라감
- `px` 단위는 고정적이라 `rem`을 사용하는 것이 좋음
- `clamp(12px, 3vw, 24px)` → 최소 12px, 최대 24px, 뷰포트 기준 가변
- CSS 기본 폰트 크기: `16px`

## 박스 모델

- `box-sizing: border-box;` → `border + padding + 내용 크기 = width` 로 계산됨

## 선택자 및 Nesting

- `.likelion`과 `__list`는 `&`로 연결 불가 (단, `:hover` 등은 가능)
- 코드가 길어질수록 뎁스가 깊어지므로 상세 선택자는 최대 2단까지 작성

## 부모-자식 관계

- 자식 요소가 커지면 부모 요소도 같이 커짐

## 기타

- `n+2` → 2부터 해당하는 요소 선택
  ```css
  a:nth-child(n + 2)::before {
  }
  ```

## 단축키

- 새로고침: `Cmd + Shift + R`
- 개발자 도구(F12)에서 스타일 우선순위 점수 확인 가능

---

## 마무리하며...

오늘도 하루를 무사히 마쳤네요!
어제 오후 7시부터 잠들어서 수업 듣는 컨디션이 좋았던 것 같습니다! ㅎㅎ
