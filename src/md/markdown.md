# 📌 **Markdown이란?**

Markdown(마크다운)은 문서를 쉽게 작성할 수 있도록 만든 경량 마크업 언어다. HTML보다 간단한 문법을 사용해 가독성이 높으며, 일반 텍스트 편집기로 작성할 수 있다.

## 🔹 **주요 특징**

- 가볍고 간결한 문법
- HTML, PDF 등 다양한 포맷으로 변환 가능
- 개발 문서, 블로그, README 파일 등에 자주 사용됨

---

## 🛠 **Markdown 기본 문법**

### 1️⃣ 제목(Header)

`#` 기호를 사용해 제목을 작성할 수 있다.

```markdown
# 제목 1

## 제목 2

### 제목 3
```

🔽 결과

# 제목 1

## 제목 2

### 제목 3

### 2️⃣ 목록(List)

- 순서 없는 목록 (`-`, `*`, `+` 사용 가능)
- 순서 있는 목록 (`1.`, `2.`, `3.` 등 사용)

```markdown
- 리스트 아이템 1
- 리스트 아이템 2
  - 서브 아이템

1. 첫 번째 아이템
2. 두 번째 아이템
   1. 하위 아이템
```

### 3️⃣ 코드 블록(Code Block)

- **인라인 코드** : `` `코드` ``
- **블록 코드** : ` ```언어`를 사용

````markdown
`인라인 코드`

```python
print("Hello, Markdown!")
```
````

````
🔽 결과
`인라인 코드`

```python
print("Hello, Markdown!")
````

### 4️⃣ 링크 & 이미지

- 링크: \`[텍스트](URL)\`
- 이미지: \`![이미지 설명](이미지 URL)\`

```markdown
[Google 바로가기](https://www.google.com)

![Markdown 로고](https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg)
```

### 5️⃣ 텍스트 스타일

```markdown
**굵게**  
_기울임_  
~~취소선~~
```

🔽 결과  
**굵게**  
_기울임_  
~~취소선~~

### 6️⃣ 인용문(Blockquote)

```markdown
> 인용문입니다.
>
> > 중첩된 인용문
```

🔽 결과

> 인용문입니다.
>
> > 중첩된 인용문

### 7️⃣ 구분선(Horizontal Rule)

```markdown
---
```

## 🔽 결과

## 🎯 **Markdown 활용 예시**

✅ **README.md 작성** → GitHub 프로젝트 설명  
✅ **Velog, GitBook** → 블로그 & 문서 정리  
✅ **노션, Typora** → 개인 문서 정리

Markdown은 배우기 쉽고 어디서든 활용할 수 있으니 자주 사용해보면 좋다! 😊
