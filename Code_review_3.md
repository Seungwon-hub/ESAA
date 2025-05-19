# Code_review_3
https://dacon.io/competitions/official/236193/codeshare/9496?page=1&dtype=recent

## 주제 및 데이터

### 주제

- 대구 교통사고 피해 예측 AI 경진대회

### About data

- **train.csv**
    - ID : 대구에서 발생한 교통사고의 고유 ID
    - 2019년부터 2021년까지의 교통사고 데이터로 구성
    - 해당 사고가 발생한 당시의 시공간 정보와 사고 관련 정보 포함
    - ECLO : 인명피해 심각도
- **test.csv**
    - ID : 대구에서 발생한 교통사고의 고유 ID
    - 2022년도의 교통사고 데이터로 구성
    - 추론 시점에서 획득할 수 있는 정보로 구성
- **sample_submission.csv**
    - ID : 추론 샘플의 고유 ID
    - ECLO : 예측한 인명피해 심각도
- **대구 빅데이터 마트 데이터**
    - [**대구 빅데이터활용센터**](https://dipbigdata.kr/pages/index.htm)에서 구축한 빅데이터 마트 데이터 중 제공 가능한 일부 데이터셋
    - 상세한 명세는 폴더 내부의 **빅데이터 마트 데이터 설명서.hwp** 참고
    - 전체 빅데이터 마트 데이터셋을 활용하기 위해서는 대구 빅데이터활용센터를 직접 방문하여 사내망 사용
- **countrywide_accident.csv**
    - 대구를 제외한 전국에서 발생한 교통사고 데이터
    - 2019년부터 2021년까지의 교통사고 데이터로 구성
- **대구 보안등 정보.csv**
    - 대구에 존재하는 보안등 관련 정보
- **대구 어린이 보호 구역 정보.csv**
    - 대구에 존재하는 어린이 보호 구역 관련 정보
- **대구 주차장 정보.csv**
    - 대구에 존재하는 주차장 관련 정보
- **대구 CCTV 정보.csv [파일]**
    - 대구에 존재하는 CCTV 관련 정보
    - 도로노선방향
        - 01 : 상행
        - 02 : 하행
        - 03 : 양방향
    - 단속구분
        - 01 : 속도
        - 02 : 신호
        - 03 : 통행위반
        - 04 : 불법주정차
        - 99 : 기타
    - 단속구간위치구분
        - 01 : 시점
        - 02 : 종점
    - 보호구역구분
        - 01 : 노인보호구역
        - 02 : 어린이보호구역
        - 99 : 기타

### 코드 리뷰

1. Understanding Domain
2. Data 설명
3. Data EDA
4. Set Hypothesis
    - Hypothesis1: ECLO가 클수록 도심 외곽 및 산에 위치해 고속도로가 존재해 위험도가 높을 것
    - Hypothesis2: 본 데이터가 누락값이 없다는 전제하에 사고다발구역 추측 가능
    - Hypothesis3: 주말 및 새벽 시간대에 사고위험도 높음
5. Data Preprocessing
    - 고속도로에 해당하는 동 별로 groupby
    - BlackSpot의 값이 큰 동 별로 groupby
6. Modeling
    - Catboost: 공간 정보 활용 측면
    - XGBoost: 시계열 데이터 활용 측면
7. Ensemble Strategy
8. Solution

### 차별 점 및 배울 점

- 데이터에 대한 이해를 더 높이기 위해 외부 데이터를 사용
