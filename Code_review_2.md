# 제주 특산물 가격 예측 AI 경진대회

https://dacon.io/competitions/official/236176/codeshare/9381?page=1&dtype=recent

### 주제

- 제주 특산물 가격 예측 AI 경진대회

### About data

1. train.csv

- train 데이터 : 2019년 01월 01일부터 2023년 03월 03일까지의 유통된 품목의 가격 데이터
- item: 품목 코드
    - TG : 감귤
    - BC : 브로콜리
    - RD : 무
    - CR : 당근
    - CB : 양배추
- corporation : 유통 법인 코드
    - 법인 A부터 F 존재
- location : 지역 코드
    - J : 제주도 제주시
    - S : 제주도 서귀포시
- supply(kg) : 유통된 물량, kg 단위
- price(원/kg) : 유통된 품목들의 kg 마다의 가격, 원 단위

2. international_trade.csv

- 관련 품목 수출입 정보
- 중량 단위 kg
- 금액 단위 천 달러

3. test.csv

- test 데이터 : 2023년 03월 04일부터 2023년 03월 31일까지의 데이터

4. sample_submission.csv

- 제출을 위한 양식
- 2023년 03월 04일부터 2023년 03월 31일까지의 price(원/kg)을 예측
- ID는 품목, 유통 법인, 지역 코드로 구성된 식별자
- 해당 ID에 맞춰 price(원/kg) 예측값을 answer 컬럼에 기입해야 함

### 코드 리뷰

1. EDA & Feature Engineering
- 데이터 이해
    - 날짜 파생 변수 생성
    - 날짜 정보 EDA
    - 시계열 파생 변수 EDA
    - 품목별 EDA
1. Modeling
- Model1: Catboost + XGBoost
- Model2: Catboost 단일 모델
1. After-Processing
2. Result
- Keyword 1: 데이터 분석을 통한 가격 변동 패턴 파악에 포커스
- Keyword 2: TG/TG외 품목 특성에 적합한 전처리 및 모델사용
- Keyword 3: Time Series Cross Validation 성능 평가

### 차별 점 및 배울 점

- Price에 루트를 씌워 예측 편차를 줄임
- Catboost는 범주형 예측에 탁월한 성능을 보이고, XGBoost는 과적합 방지에 탁월함
