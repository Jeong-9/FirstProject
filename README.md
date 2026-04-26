# C#과 Winform으로 만든 일정관리 프로그램

## 1. 프로젝트 개요
C#과 WinForms, MySQL을 기반으로 제작한 일정관리 프로그램입니다.  

## 2. 프로젝트 배경
WinForm과 MySQL 기반으로 
누구나 쉽고, 안정적으로 관리 할 수 있는
일정 관리 프로그램을 구현하고자 하였습니다.

- 공용 캘린더 일정과 개인 캘린더 일정을 월별로 한눈에 확인 가능한 대시보드
- 복잡하지않은 CRUD 화면을 통한 간편한 일정관리
- 특정 키워드 또는 기간별 일정 필터링(검색)

## 3. 프로젝트 목적
- 안정성 : RDBMS를 활용하여 데이터를 체계적이고 안전하게 관리
- 편의성 : 복잡한 메뉴얼이 필요하지 않은 사용자 중심 CRUD 인터페이스
- 가시성 : 차별화된 일정 표시 기능을 통해 직관적인 스케쥴 정보 식별
- 신속성 : 변경된 정보를 실시간 반영 및 빠른 작업 환경 제공

## 🛠️ 4.  개발 환경
### Visual Studio(C#, WinForm)
-Visual Studio가 제공하는 환경에서 C#과 WinForms을 사용하여 UI 및 기능 구현 
### MySQL
-일정, 공유그룹, 사용자의 정보를 효율적으로 관리하기위한 데이터베이스
### GitHub
-프로젝트 소스 코드 통합
###Sourcetree
-복잡한 Git 명령어를 마우스 클릭만으로 처리할 수 있게 도와주는 도구

### 5.시스템 흐름도(Architecture)
- 로그인
<img width="1727" height="1584" alt="image" src="https://github.com/user-attachments/assets/5859c5b6-37d1-4e77-8900-8f0f1caff78d" />
*사용자가 프로그램에 접속하여 아이디를 입력하면 정보 일치 여부를 확인.
아이디 찾기 기능을 제공하며, 올바른 비밀번호가 존재하는지 검증이 완료되면 메인 화면으로 진입함
이를 통해 프로그램의 첫 시작인 보안과 사용자 인증을 처리

- 일정 관리
<img width="1400" height="1575" alt="image" src="https://github.com/user-attachments/assets/11b9392c-1eb7-488b-9d23-26eba7e5db52" />
*사용자가 캘린더 화면에서 특정 날짜를 선택하면 일정을 등록할 수 있는 창이 뜸.
등록을 진행하면 입력된 데이터가 DB에 저장되고, 즉시 캘린더 화면에 일정이 표시됨.
이미 등록된 일정은 '상세보기'를 통해 확인할 수 있으며, 여기서 사용자의 선택에 따라 일정을 수정하거나 삭제할 수 있음.
이 모든 변경 사항은 실시간으로 DB에 업데이트되거나 삭제되어 화면에 반영되는 직관적인 CRUD 흐름을 가집니다.

- 카테고리 관리
<img width="1364" height="1579" alt="image" src="https://github.com/user-attachments/assets/a6f16856-de62-46d0-b8fc-50cdd165aac8" />
*사용자는 본인만의 캘린더뿐만 아니라 공유 캘린더를 추가로 생성할 수 있음.
추가할 멤버와 캘린더의 정보를 입력하고 이렇게 생성된 그룹 정보 역시 DB에 연동되어 캘린더 화면에 카테고리로 분류되어 나타남

###📸스크린 샷(Screenshots)
- 캘린더 화면
  ****<img width="3192" height="1477" alt="image" src="https://github.com/user-attachments/assets/66851544-7a6b-4557-b5e8-4bb9f71d9427" />

- 로그인
<img width="802" height="450" alt="image" src="https://github.com/user-attachments/assets/7c6142ee-b743-4cc4-9f97-bee0a3f4337e" />

- 회원가입
  <img width="537" height="696" alt="image" src="https://github.com/user-attachments/assets/60b1cf31-d873-41f2-8033-2e63536a6a1d" />

- 아이디 찾기
  <img width="800" height="449" alt="image" src="https://github.com/user-attachments/assets/8fd331e1-dda2-49b1-8157-f7acd82c8705" />

- 비밀번호 찾기(임시 비밀번호 발송)
<img width="796" height="455" alt="image" src="https://github.com/user-attachments/assets/94ac80dd-67c9-4256-8dac-8edc719f249c" />
<img width="1079" height="833" alt="image" src="https://github.com/user-attachments/assets/3562f4dc-cbfe-49a1-8800-6a606afbd627" />

- 비밀번호 변경
<img width="1342" height="800" alt="image" src="https://github.com/user-attachments/assets/e9095aa7-515d-46e2-99e4-64e15a5748bc" />

## 6. 주요 담당 기능
### 로그인
- 아이디와 비밀번호를 입력하여 사용자 인증 수행
- 로그인 성공 시 사용자 세션 유지

### 회원가입
- 사용자 정보 입력 후 DB에 회원 정보 저장
- 입력값 확인 및 중복 검사 수행

### 아이디 찾기
- 가입 시 입력한 사용자 정보를 통해 아이디 조회 가능

### 비밀번호 찾기
- 가입된 이메일 확인 후 임시 비밀번호 생성
- 실제 이메일로 임시 비밀번호 발송

### 비밀번호 변경
- 임시 비밀번호 또는 기존 비밀번호 확인 후 새 비밀번호로 변경 가능

### 핵심 클래스
- JoinMember  
  회원가입, 로그인, 아이디 찾기, 비밀번호 찾기, 비밀번호 변경 관련 기능 담당


- UserSession  
  로그인한 사용자 정보를 프로그램 전역에서 유지

  ## 시연 영상
https://youtu.be/QPl6Y-iZQ0Q
