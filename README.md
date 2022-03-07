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
 
### 1) Data Type    
 
 ABAP Program 내에서 사용할 Variable(변수)의 타입을 정의하기 위해 사용한다. 아래와 같이 크게 3가지로 분류된다.    

 - Predefined ABAP Types : SAP 커널 레벨에 정의되어 있는 데이터 타입으로, C(문자), D(날짜), F(지수형 실수), I(정수), N(자연수), P(소수형 실수), T(시간), X(십육진수) 등이 존재한다.    
 - Local Types in Programs : ABAP Program 내에서 정의하여 해당 프로그램에서만 사용하는 데이터 타입으로, 여러 타입의 필드를 조합한 Structure 형태의 타입을 정의하여 사용할 수 있다.    
 - Types in the ABAP Dictionary : ABAP Dictionary에 등록되어 있는 Object의 데이터 타입으로, 모든 ABAP Program에서 사용 가능하다.    
 
### 2) Variable(변수) 선언    
 
 ABAP Program 내에서 사용하는 Variable(변수) 선언은 Data Type을 참조하는 방식으로 이루어진다. 주요 구문은 아래와 같다.    

```











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








