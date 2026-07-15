# Codyssey_KDJ B-3

### 노코드 자동화:워크플로우 설계

### 목차
1. [프로젝트 1] 자동화 도구 비교 구현

     1-1. 동일한 자동화 워크플로우 2개 이상의 도구 구현

     1-2. 각 도구별 워크플로우 구성 화면

     1-3. 실행 결과 화면 캡처

     1-4. 비교 분석 보고서

2. [프로젝트 2] 자유 주제 자동화 설계 및 구현 

     2-1. 자동화할 반복 업무 1개 정의
     
     2-2. 자동화 도구 1개 선정 및 선정 이유 작성
     
     2-3. 워크플로우 설계 문서
     
     2-4. 구현 화면 캡쳐 
    
     2-5. 실행 결과 화면 캡처
 
## Make / Zapier 각 도구의 과금 리스크 완화를 위해 무료 플랜만으로 만들어진 결과물입니다.

[프로젝트 1]

### 1-1 동일한 자동화 워크플로우 개요
본 워크플로우는 고객의 문의 유형(일반 문의 vs 견적 요청)에 따라 자동으로 데이터를 분류하여 상이한 템플릿의 이메일 알림을 보조하는 CS 인바운드 자동화 시스템입니다.

     구성 형태

     Trigger (트리거): Google Forms에 새로운 설문 응답 접수

     Action 1 (액션 1): Google Sheets 스프레드시트에 해당 고객 정보 및 문의 데이터 자동 추가 기록

     Filter / Router (분기): 문의 유형 필터링 (경로 A: 일반 문의 / 경로 B: 견적 요청)

     Action 2 (액션 2): 각각의 경로에 맞춘 개인화 및 시각적 CSS가 적용된 Gmail 메일 발송

### 1-2. 각 도구별 워크플로우 구성 화면 상세 분석

# Make (메이크) 워크플로우 구성
시각적 구조: 좌에서 우로 흐르는 유동적인 원형 노드(Node) 형태

트리거: Google Forms (Watch Responses) 모듈이 작동 (폴링 주기 기반)

연결 및 분기

     Google Sheets (Add a Row) 추가 후, 중앙의 녹색 Router 모듈을 통해 위아래 2갈래의 경로로 깔끔하게 나뉩습니다.

     각 갈래의 중간 연결선에 필터(견적 요청, 일반 문의)를 직관적으로 걸어두어 조건 분기를 한눈에 알아볼 수 있습니다.

<div>
 <img width="810" height="408" alt="Image" src="https://github.com/user-attachments/assets/1e572320-a458-426c-b87b-69b10595307f" />
<div>

Zapier (재피어) 워크플로우 구성
시각적 구조: 위에서 아래로 흐르는 수직 계층형 탑다운(Top-down) 카드 형태

트리거: 1. Google Forms (New Form Response)로 시작

연결 및 분기:

     Google Sheets (Change Sheet Properties)를 거친 후, 3. Split into paths (Paths 기능)를 통해 좌우 Path A와 Path B 하위 갈래로 나뉩니다.

     각 하위 갈래 밑에 조건 필터링(4/6. Path conditions)과 최종 지메일 액션(5/7. Send Email)이 직렬 구조로 배치되어 있습니다.

<div>
<img width="534" height="649" alt="Image" src="https://github.com/user-attachments/assets/4039984f-9906-4aad-a2bc-0d75e53ba307" />
<div>

### 1-3. Make vs Zapier 자동화 도구 비교 분석 보고서

[📄 PDF 비교 분석 보고서 바로 읽기](make-zapier%20reports.pdf)
