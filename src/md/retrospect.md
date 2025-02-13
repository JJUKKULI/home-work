# 🦁멋쟁이사자 FE 13기 회고록 no.1

요새 날씨가 추운 지금 새로운 시도를 해보고 있었는데요...

### 바로 "부트캠프"

컴공과 4학년을 앞두고 제대로 된 팀 프로젝트 경험이나 서비스 배포 등을 해보지 못한 저는 이에 대한 갈망이 있었습니다...

### 멋쟁이사자 FE 13기 합류

1. **노베이스 가능**
2. **기초가 탄탄한 커리큘럼**
3. **적당한 횟수의 큰 프로젝트 경험**  
   _feat. 해커톤_
4. **되도록 빠르게 시작**

위의 이유들로 인해 **멋사 FE 부캠**을 선택하게 되었습니다! 🎉🎉

나름 **휴학도 신청**하고 1년 동안 자격증 공부와 함께 첫 스타트를 끊는 공부인 만큼  
꾸준하고 성실하게 임하여 **훌륭한 주니어 개발자**가 되길 바랍니다.

**파이팅!!** 💪💪

# 🦁멋쟁이사자 FE 13기 회고록 no.2

부트캠프 시작 후 정신없이 하루들을 보내다보니 벌써 시작한지 4일째가 되는 날이군요....

이번 페이지부터 공부한 내용을 회고하려고 합니다 📑

# node.js

node.js 는 브라우저가 아닌 외부에서 CLI(명령어 인터페이스)와 서버 측 스크립트를 작성할 수 있는 무료 오픈 소스 크로스 플랫폼 javaScript 런타임 환경 입니다.

### **키워드** 🔑

javascript
open source
every where

### 실습

1.  likelion-bootcamp 폴더 하위에 learn-node라는 폴더 생성 후 이동

```
 cd
 cd likelion-bootcamp
 mkdir learn-node
 cd learn-node
```

2. learn-node 폴어데 ehco 명령을 사용하여 아래의 내용으로 sum.js 파일 생성

```
echo 'let sum = 0;
for (let i = 1; i <= 100; i++) {
  sum = sum + i;
}

console.log(sum);' > sum.js
```

3. node환경에서 sum.js를 실행

```
node sum.js
```

# NPM

NPM은 "node package manager"의 약자로, 자바스크립트 프로그래밍 환경에서 패키지를 설치하고 관리해주는 도구

#### = 패키지매니저

1. 개발시 다양한 패키지를 쉽게 설치, 관리
2. 타인과 공유, 배포 가능

### 실습

npm은 node.js를 설치하면 같이 설치 됌, 설치여부 확인 명령어

```
npm --version
npm -v
```

만약 npm을 최신버전으로 업데이트

```
npm install --global npm@latest
or
npm i -g npm@latest
```

#### npm을 활용하여 패키지 설치

1. 전역(Global)로 설치

```
npm install --global <패키지>
or
npm i -g <패키지>
```

2. 로컬(Local)로 설치

```
npm install <패키지>
or
npm i <패키지>
```

#### npm을 활용하여 패키지 삭제

1. 전역(Global)에 설치된 패키지 삭제

```
npm uninstall --global <패키지>
or
npm un -g <패키지>
```

2. 로컬(Local)에 설치된 패키지 삭제

```
npm uninstall <패키지>
or
npm un <패키지>
```

#### npm을 활용하여 패키지 설치 및 사용 예시

1. package.json

```
npm init -y
```

2. add-gitignore 패키지 설치

```
npm install --global add-gitinore
```

3. 설치한 add-gitignore 패키지를 사용하여 .gitignore 생성

```
add-gitignore node windows osx visualstudiocode
or
npx add-gitignore node windows osx visualstudiocode
```

### package.json

package.json은 Node.js 프로젝트에서 사용되는 메타데이터 파일

1. 의존성 관리
2. 스크립트 정의
3. 프로젝트 정보 제공
4. 패키지 배포 정보

package.json 파일은 프로젝트 루트 디렉토리에 위치. npm init 명령어를 통해 초기화하거나 수동 작성 가능. npm 명령어를 사용하여 패키지 설치시, 자동으로 package.json 파일에 의존성 정보 업데이트

ex) scripts 정의

# Live-server

live-server는 live reload 기능을 갖춘 개발 서버. vscode의 확장 프로그램으로 설치할 수도 있지만, 프로젝트 폴더에 local로 설치하여 사용 가능.

-> **협업** 유리

### live-server 설치

1. learn-node 라는 폴더 하위에 src 폴더 생성하고 해당 폴더에 index.html 파일 생성

```
mkdir src
touch src/index.html
```

2.  index.html 파일에 아래 코드 추가

```
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>NPM 패키지 설치(live-server)</title>
</head>
<body>
  <h1>live Server 실행</h1>
</body>
</html>
```

3. learn-node 라는 폴더에 live-server 패키지를 local로 설치

```
npm i -D live-server
```

4. live-server 실행을 위해 터미널에 다음을 입력

```
npx live-server src --port=8090 --host=localhost --no-browser
```

5. package.json 에 다음을 추가

```
"scripts": {
	"start": "live-server src --port=8080 --host=localhost --no-browser"
}
```

6. npm 스크립트 명령을 사용하여 live-server 실행

```
npm start
```

# Prettier

prettier는 일관된 스타일의 코드를 자동으로 형식화 해주는 도구(코드포멧터)
javascript, typescript, html, css, json 등 다양한 언어 지원

### 키워드🔑

자동 포멧팅
일관성 유지
플러그인 지원
구성가능

### 설치방법

prettier는 npm을 통해 설치할 수 있으며 다음 명령어를 터미널에 입력

```
npm install --save-dev prettier
or
npm i -D prettier
```

환경구성 파일 작성

```
module.exports = {
  // 화살표 함수 식 매개변수 () 생략 여부 (ex: (a) => a)
  arrowParens: 'always',
  // 닫는 괄호(>) 위치 설정
  // ex: <div
  //       id="unique-id"
  //       class="contaienr"
  //     >
  htmlWhitespaceSensitivity: 'css',
  bracketSameLine: false,
  // 객체 표기 괄호 사이 공백 추가 여부 (ex: { foo: bar })
  bracketSpacing: true,
  // 행폭 설정 (줄 길이가 설정 값보다 길어지면 자동 개행)
  printWidth: 80,
  // 산문 래핑 설정
  proseWrap: 'preserve',
  // 객체 속성 key 값에 인용 부호 사용 여부 (ex: { 'key': 'xkieo-xxxx' })
  quoteProps: 'as-needed',
  // 세미콜론(;) 사용 여부
  semi: true,
  // 싱글 인용 부호(') 사용 여부
  singleQuote: true,
  // 탭 너비 설정
  tabWidth: 2,
  // 객체 마지막 속성 선언 뒷 부분에 콤마 추가 여부
  trailingComma: 'es5',
  // 탭 사용 여부
  useTabs: false,
};
```

포멧 제외 항목 설정
.prettierignore 파일을 생성하고 제외 할 항목 추가

```
# 포멧팅 제외
# node_modules 폴더 무시
node_modules/

# 빌드 폴더 무시
dist/
build/

# 특정 파일 무시
*.min.js
*.log

# 특정 디렉토리 및 하위 파일 무시
coverage/
```

### 명령어의 동작

**--check** : 지정된 파일들이 prettier의 포멧팅 규칙을 따르고 있는지 확인 & 포멧이 맞지 않는 파일이 있으면 실패 메세지 출력
**--write** : prettier 규칙에 맞지 않는 파일을 포멧팅한 후, 해당 내용을 원본 파일에 덮어씀(이미 맞는 파일은 수정X)
**--ignore-path .gitignore** : prettier가 기본적으로 사용하는 .prettierignore 파일 대신, .gitignore 파일을 무시 목록으로 사용하도록 지정

### 포멧팅

코드 포멧을 check(체크)

```
npx prettier --check .
```

코드모멧팅을 write(적용)

```
npx prettier --write .
npx prettier --write . --ignore-path .gitignore
```

### 별칭 명령 등록

package.json 파일에 format 명령 등록

```
"scripts": {
  "format": "prettier --write . --ignore-path .gitignore",
}
```

별칭으로 등록된 명령 실행시 코드 포멧팅 쉬움

```
npm run format
```

## 📑 4일차 완료

이렇게 prettier까지 활용하며 4일차가 끝났습니다!

마지막까지 힘낼 수 있길!
다들 오늘 하루 수고하셨습니다:)

# 🦁멋쟁이사자 FE 13기 회고록 no.3

눈이 오는가 싶더니 오늘부터 날이 좀 풀리는가 봅니다
하지만 감기가 유행 중이므로 집콕을 연명....

각설하고 5일차 회고록 시작하겠습니다:) 📑

# HTML

기본적인 HTML 파일의 개요는 다음과 같다

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Machine Learning Workshop</title>
    <meta name="viewport" content="width=device-width" />
  </head>
  <body>

  </body>
</html>
```

## Tag

= 마크업 언어

- xml 이용시 html에서 지정된 tag 사용 가능

```
<회사명>멋쟁이사자 주식회사</회사명>
```

**Nesting**은 태그 중첩을 의미 (예시)

```
<p>this paragraph has some
 <strong><em>어쩌구저쩌구</em></strong>
 content</p>
```

따라서 HTML은 기본적으로 **트리구조**로 구성

**Empty Element** (빈요소)

- 클로징태그 X
- ex) img, input

```
<input type="range">
<img src="switch.svg" alt="light switch">
```

# Emmet

HTML, XML 등 문서 등을 편집할 때 빠른 코딩을 위해 사용하는 플러그인 (vscode에는 기본적으로 설치)

> https://docs.emmet.io/cheat-sheet/

cheat-sheet 로 각 문서별 emmet의 구성을 볼 수 있다

### vscode emmet 설정

commend(ctrl) + , 를 누르면 설정창으로 이동되는데 검색창에 emmet이라고 검색하면 다양한 설정을 볼 수 있다
ex) html의 lang 변경

```<!DOCTYPE html>
<html lang="ko-KR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>멋사 프론트엔드 부트캠프 13기</title>
</head>
<body>
  <h1>HTML/CSS</h1>
  <ul>
    <li><a href="./src/html/01-basic-structure.html">HTML 기본 구조</a></li>
  </ul>
</body>
</html>
```

## 단축키 🗝️

commend + p = vscode 검색창
commend + shift + p = 검색명령창( > 추가 )
commend + a 전체 글 선택
commend + / = 코드분할
commend + , = setting창
commend + f = 웹페이지 서치
commend + 클릭 = 링크이동

### 이후 실습 중 기억 🤯

쌤의 git 파일을 local로 가져오기

```
git clone https://github.com/seulbinim/ssam-html-css.git
```

```
cd ssam-html-css
npm i
```

likelion-bootcamp 파일로 이동하고, cp를 사용하여 쌤의 파일과 디렉터리을 복사

```
cd ..
cp ssam-html-css learn-html-css
cp -r ssam-html-css learn-html-css
```

기존 remote(원격) origin을 지우고 내 git 저장소로 연결

```
remote rm origin
remote add origin https://github.com/JJUKKULI/learn-html-css.git
```

이후 learn-html-css 폴더에서 필요한 파일 추가하고 ls로 확인하는 작업

```
cd learn-html-css
code .
code index.html
ls src
mkdir src/html
ls src
touch src/html/01-basic-structure.html
ls src
```

live-server를 extension에서 설치했다가 삭제하면서 오류땜에 다시 삭제 및 설치 😭

```
npm un -D live-server
npm i -D live-server
```

이후 git add로 변경 사항 추가 및 commit(이력)작성

```
git add .prettierrc.cjs
git commit
git add index.html
git commit
git log --oneline
git status
git add package-lock.json
git commit
git log --oneline
git status
git add .
git commit
git log --oneline
```

마지막쯤 문제 발생 npm run format 하면 Prettier 실행하려고 했는데 package.json 파일을 찾을 수 없다고 함

1.  package.json 있는지 확인
2.  prettier가 설치되어 있는지 확인
3.  node_modules가 손상된 경우
4.  scripts에 format이 있는지 확인

위 네가지의 해결책을 chat.gpt가 제시
이중 1,2,4번은 문제 없었고 3번을 이용해 해결

> node_modules와 package-lock.json을 삭제 후 재설치

```
rm -rf node_modules package-lock.json
npm install
```

```
npm run format
```

warning은 뜨지만 오류검출 X 👍🏻

### 📑 5일차 회고록을 마무리하며...

오류도 중간에 뜨고 어지러웠지만 그 덕분에 git관련 학습과 복습을 추가로 진행하며 블로그를 작성하였다...(크흡 ㅠㅠ)

내일 하루도 힘내겠습니다!
다들 감기 조심하고 미끄러짐 주의하세요!
그럼 이만..🏃🏻
