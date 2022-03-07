# SAP ABAP    

SAP ABAP | SAP ERP    

<details>
<summary>목차 및 링크</summary>
<div markdown="1">

> [1. ABAP란?]()    
> > [1) ABAP]()    
> > [2) ABAP Program 구조]()    
> > [3) ABAP Dictionary]()    
> 
> [2. ABAP Programming]()    
> > [1) ABAP Programming 초급]()    
> > [2) ABAP Programming 중급]()    
> > [3) ABAP Programming 고급]()    

</div>
</details>
 
-----
 
## 1. ABAP란?

### 1) ABAP

 "Advanced Business Application Programming"의 약어로, SAP ERP 시스템에서 사용하는 프로그래밍 언어이다.    

### 2) ABAP Program 구조    

 Component(컴포넌트) > Package(개발 클래스) > Object(오브젝트)    

 ABAP Program 구조는 위와 같이 이루어져있으며, Object(오브젝트)에는 Program, Function, Dictionary Object 등이 포함된다.    

### 3) ABAP Dictionary

 SAP ERP의 ABAP Dictionary는 3가지 대분류와 7가지 소분류를 사용하여 Dictionary Object를 구분시킨다.    
 분류 항목은 아래와 같으며, T-code SE11에서 각 분류 항목으로 나눠진 Dictionary Object를 조회할 수 있다.    
 
 - Database Object : Database Table, View    
 - Type Definition : Data Type, Type Group    
 - ABAP Tools : Domain, Search Help, Lock Object    

 7가지 소분류에 대한 정의는 아래와 같다.    

 - Database Table : DB 내에 실제로 저장되어 있는 물리 데이터    
 - View : 하나 이상의 Database Table로 생성한 논리 데이터    
 - Data Type : 프로그램에서 사용할 수 있도록 정의된 데이터 타입    
 - Type Group : 데이터 타입을 모아둔 그룹    
 - Domain : Data Element에 할당되어 사용되는 기술적 속성 정의    
 - Search Help :     
 - Lock Object :     
 
-----
 
## 2. Data Type & Variable
 
### 1) Data Type 종류    
 
 ABAP Program 내에서 사용할 Variable(변수)의 타입을 정의하기 위해 사용한다. 아래와 같이 크게 3가지로 분류된다.    

 - Predefined ABAP Types : SAP 커널 레벨에 정의되어 있는 데이터 타입으로, C(문자), D(날짜), F(지수형 실수), I(정수), N(자연수), P(소수형 실수), T(시간), X(십육진수) 등이 존재한다.    
 - Local Types in Programs : ABAP Program 내에서 정의하여 해당 프로그램에서만 사용하는 데이터 타입으로, 여러 타입의 필드를 조합한 Structure 형태의 타입을 정의하여 사용할 수 있다.    
 - Types in the ABAP Dictionary : ABAP Dictionary에 등록되어 있는 Object의 데이터 타입으로, 모든 ABAP Program에서 사용 가능하다.    
 
### 2) Data Type & Variable 선언    
 
 ABAP Program 내에서의 Variable(변수) 선언은 Data Type을 참조하는 방식으로 이루어진다. 주요 구문은 아래와 같다.    
 
```ABAP
** Predefined ABAP Types 참조 변수 선언
DATA : 
  int TYPE I VALUE 123, " VALUE 구문은 초기값 설정
  float TYPE F, " F 타입의 경우 반올림 오류가 발생하므로, 실수는 일반적으로 P 타입 사용
  pack TYPE P DECIMALS 4, " DECIMALS 구문은 P 타입에서만 사용 가능하며, 최대 14 자리수의 소수점 설정
  time TYPE T,
  text1 TYPE C,
  text2(2) TYPE C,
  text3 TYPE C LENGTH 4, " LENGTH 구문은 C, N, X, P 타입에서만 사용 가능하며, 길이 설정
  ltext TYPE string.

** Local Types in Programs 참조 변수 선언
* Local Type 선언
TYPES : 
  BEGIN OF struct,
    num1 TYPE I,
    num2 TYPE F,
  END OF struct.
* 변수 선언
DATA : 
  gs_struct TYPE struct, " TYPE 구문 뒤엔 Type명
  gv_num1 LIKE gs_struct-num1. " LIKE 구문 뒤엔 이미 Type 할당된 Object명

** Types in the ABAP Dictionary 참조 변수 선언
DATA : 
  gv_carrid TYPE s_carr_id, " Data Element 참조 변수 선언
  gv_connid TYPE sflight-connid. " Table Field 참조 변수 선언
```
 
 변수명 길이는 최대 30자이며, 네이밍 룰은 아래와 같다.    
 
 - 첫 번째 글자(범위) : G(글로벌 변수) / L(로컬 변수)
 - 두 번째 글자(타입) : V(단일 변수) / S(구조체 변수) / T(테이블 변수) / R(범위 변수) / C(상수) / O(클래스)
 - 세 번째 글자(구분자) : _
 - 나머지 글자 : 의미 요약
 
-----
 
## 3. 연산 및 출력
 
### 1) 산술 연산
 
 ABAP Program에서 쓰이는 산술 연산은 아래와 같다.
 
```ABAP
num_sum = num1 + num2. " 더하기
ADD num2 TO num1. " 더하기
num_substract = num1 - num2. " 빼기
SUBSTRACT num2 FROM num1. " 빼기
num_multiply = num1 * num2. " 곱하기
MULTIPLY num1 BY num2. " 곱하기
num_divide = num1 / num2. " 나누기
DIVIDE num1 BY num2. " 나누기
num_quotient = num1 DIV num2. " 몫
num_remainder = num1 MOD num2. " 나머지
num_power = num1 ** num2. " 제곱
```

### 2) 논리 연산
 
 ABAP Program에서 쓰이는 논리 연산은 아래와 같다.
 
```ABAP

```

### 3) 문자열 연산

 ABAP Program에서 쓰이는 문자열 연산은 아래와 같다.
 
```ABAP

```
 
### 4) 할당 연산

 ABAP Program에서 쓰이는 문자열 연산은 아래와 같다.
 
```ABAP

```
 
### 5) 기타 연산
 
 ABAP Program에서 쓰이는 기타 연산은 아래와 같다.
 
```ABAP

```
 
-----
 
## 2. ABAP Programming    

### 1) ABAP Programming 초급    

 ABAP Programming 관련 초급 메뉴얼 목록을 작성하고자 한다. 아래 "목록"을 참고하면 되겠다.    

<details>
<summary>목록</summary>
<div markdown="1">

> 코어 모듈
> - MM : "Material Management"의 약어로, 구매 및 자재 관리 모듈
> - PP : "Production Planning"의 약어로, 생산 관리 모듈
> - SD : "Sales and Distribution"의 약어로, 영업 및 유통(물류) 관리 모듈
> - FI : "Financial"의 약자로, 재무 회계 모듈 (외부 보고용 회계)
> - CO : "Controlling"의 약자로, 관리 회계 모듈 (내부 전략용 회계)
> - HR : "Human Resources"의 약어로, 인사 관리 모듈
> - BW : "Business Warehouse"의 약어로, 데이터 관리 모듈
> - BI : "Business Intelligence"의 약어로, 데이터 분석 및 리포팅 모듈
> 
> 서브 모듈
> - QM : "Quality Management"의 약어로, 품질 관리 모듈
> - IM : "Investment Management"의 약어로, 수출입 및 투자 관리 모듈
> - LE : "Logistics Execution"의 약어로, 재고 및 보관 관리 모듈
> - PM : "Plant Management"의 약어로, 설비 관리 모듈
> - TR : "Treasury"의 약자로, 자금 관리 모듈
> - FB : "Firm Banking"의 약어로, 펌뱅킹 관리 모듈 (은행 업무)
> - PI : "Process Integration"의 약어로, non-SAP 프로그램 데이터 연동 관리 모듈

</div>
</details>

### 2) ABAP Programming 중급    

### 3) ABAP Programming 고급    








