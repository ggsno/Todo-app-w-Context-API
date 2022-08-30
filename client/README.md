# Todo app

- 원티드 프리온보딩 프론트엔드 코스 선발 과제
- 사용 기술 : <img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black"/> <img src="https://img.shields.io/badge/Typescript-3178C6?style=flat&logo=typescript&logoColor=white"/> <img src="https://img.shields.io/badge/ReactRouter-CA4245?style=flat&logo=reactrouter&logoColor=white"/> <img src="https://img.shields.io/badge/StyledComponents-DB7093?style=flat&logo=styledcomponents&logoColor=white"/>

## 최종 구현 화면

### 회원가입 및 로그인

https://user-images.githubusercontent.com/46833758/185788055-b6631846-65dc-414a-8556-58757e15f8c8.mp4

- 유효하지 않은 입력일 시 입력창 하단에 즉각 피드백
- 유효하지 않은 폼이 하나라도 존재하면 제출 버튼 비활성화
- 회원가입 성공시 todo list 화면으로 이동

### todo list

https://user-images.githubusercontent.com/46833758/185788115-b9ff1462-3f76-4414-99b9-831e2fd159b6.mp4

- 화면 중앙 입력 창에서 할 일 입력 후 제출(enter 혹은 추가버튼 클릭)시 할 일 추가
- 할 일 요소 좌측에 한 일 체크, 우측에 수정모드 버튼과 삭제버튼

## 설치, 환경설정 및 실행 방법

- node 버전 : v16.16.0

` yarn`

` yarn start`

## 구현 요구 사항 목록

### **:: 1. 로그인 / 회원가입**

- `/` 경로에 로그인 / 회원가입 기능을 개발해주세요
  - 페이지 안에 이메일 입력창, 비밀번호 입력창, 제출 버튼이 포함된 형태로 구성해주세요
  - 로그인, 회원가입을 별도의 경로로 분리해도 무방합니다.

### **Assignment1** [구현완료]

- 이메일과 비밀번호의 유효성 검사기능을 구현해주세요
  - 이메일 조건: `@` 포함
  - 비밀번호 조건: 8자 이상
  - 입력된 이메일과 비밀번호가 위 조건을 만족할 때만 버튼이 활성화 되도록 해주세요
  - 보안 상 실제 사용하고 계신 이메일과 패스워드말고 테스트용 이메일, 패스워드 사용을 권장드립니다.

### **Assignment2** [구현완료]

- 로그인 API를 호출하고, 올바른 응답을 받았을 때 `/todo` 경로로 이동해주세요
  - 로그인 API는 로그인이 성공했을 시 Response Body에 JWT를 포함해서 응답합니다.
  - 응답받은 JWT는 로컬 스토리지에 저장해주세요

### **Assignment3** [구현완료]

- 로그인 여부에 따른 리다이렉트 처리를 구현해주세요
  - 로컬 스토리지에 토큰이 있는 상태로 `/` 페이지에 접속한다면 `/todo` 경로로 리다이렉트 시켜주세요
  - 로컬 스토리지에 토큰이 없는 상태로 `/todo`페이지에 접속한다면 `/` 경로로 리다이렉트 시켜주세요

---

### **:: 2. 투두 리스트**

### **Assignment4** [구현완료]

- `/todo`경로에 접속하면 투두 리스트의 목록을 볼 수 있도록 해주세요
- 리스트 페이지에는 투두 리스트의 내용과 완료 여부가 표시되어야 합니다.
- 리스트 페이지에는 입력창과 추가 버튼이 있고, 추가 버튼을 누르면 입력창의 내용이 새로운 투두 리스트로 추가되도록 해주세요

### **Assignment5** [구현완료]

- 투두 리스트의 수정, 삭제 기능을 구현해주세요
  - 투두 리스트의 개별 아이템 우측에 수정버튼이 존재하고 해당 버튼을 누르면 수정모드가 활성화되고 투두 리스트의 내용을 수정할 수 있도록 해주세요
  - 수정모드에서는 개별 아이템의 우측에 제출버튼과 취소버튼이 표시되며 해당 버튼을 통해서 수정 내용을 제출하거나 수정을 취소할 수 있도록 해주세요
  - 투두 리스트의 개별 아이템 우측에 삭제버튼이 존재하고 해당 버튼을 누르면 투두 리스트가 삭제되도록 해주세요

## 사용한 프레임워크 및 라이브러리

### axios

- 구현의 편의를 위함
  - 토큰이 필요한데 없는 request를 interceptor를 이용해 한곳에서 걸러줌
  - instance로 비슷한 api들을 묶어서 이용

### styled-components

- 스타일링을 하나의 컴포넌트에서 함께 관리해 응집성을 높혀 간결한 폴더구조 구축을 위함
- 공통된 컴포넌트는 common 컴포넌트에서 관리, 상속으로 재사용

## 폴더 구조

```
src
├─components // 컴포넌트 단위로 구현된 뷰, 각 컴포넌트에 필요한 state가 뷰와 함께 있음
│  ├─auth
│  │  └─hooks
│  ├─common
│  ├─layout
│  └─todo
│     └─hooks
├─context // 컨텍스트
├─hooks // 공통 hooks
├─pages // 페이지 단위 뷰, components의 컴포넌트들을 조합해 페이지 구성
│  ├─auth
│  └─todo
├─router
├─services // 서버 관련 코드
│  ├─api
│  └─model // 도메인 관련 스키마
└─utils
```

## 주안점

### 관심사의 분리와 재사용성

- 컴포넌트 단위로 view를 구성하고 각 컴포넌트에 필요한 로직은 hooks로 분리
- 재사용 가능한 컴포넌트는 common으로 분리
- context를 이용해 props drilling 최소화

### 사용자 경험 개선

- 로그인이나 회원가입 시
- 수정 모드 버튼 클릭 시 focus가 수정input으로 이동
- enter키로 입력 완료 및 수정 완료

## 한계점 및 개선 사항

### 사용자 피드백 UI/UX

- 로딩 시 로딩 컴포넌트나 스켈레톤 미구현
- 에러 시 대부분 alert가 나오도록 처리를 했는데 alert창은 닫힐 때 까지 다른 모든 인터페이스에 접근할 수 없으므로 중요한 상항(삭제, 수정 등 데이터가 변경되는 상황)이 아니라면 지양해야함

### 수정 시 이전 상태 깜빡임

- todo를 수정하고 갱신 시 최신 todo 목록을 반영하고 다시 렌더링하는 과정에서 미처 수정되지 못한 상태가 잠시 보임

### 에러 핸들링

- 각각의 에러에 더 적합한 행동을 구현할 수 있음

## 참고 | 과제 repo

https://github.com/walking-sunset/selection-task
