# Code review_1

https://dacon.io/competitions/official/236068/codeshare/11596?page=1&dtype=recent

### 주제

- 당뇨병 위험 분류 예측

### train.csv / test.csv : Diabetes 데이터

- Pregnancies : 임신횟수
- Glucose : 포도당 농도
- BloodPressure : 혈압
- SkinThickness : 피부두께
- Insulin : 인슐린
- BMI : 체질량지수
- DiabetesPedigreeFunction : 당뇨병 혈통 기능
- Age : 나이
- Outcome : 당뇨병 여부(0: 발병되지 않음, 1: 발병)

### 코드 리뷰

- null값 확인
- 히트맵 시각화 통한 결측치 확인
- 박스플롯을 이용한 이상치 확인
- 도메인 지식을 통한 이상치, 결측치 해결
- 모델링
    - feature와 target 분리
    - 데이터 분할
    - KFold로 분리
    - Voting_Classifier로 학습
    - 훈련 데이터 확장
    - Stacking 모델 구성
    - Threshold 튜닝
    - 최적의 F1 Score 위한 임계값 찾기
- 최종 성능 평가
- 예측 및 저장

### 차별 점 및 배울 점

- 히트맵 시각화를 이용하여 결측치를 확인한 점
- 인슐린에 대한 기본 지식을 통해 결측치 해결 - 예) 공복일 때 인슐린 수치가 0일 수도 있음
- 테스트 데이터로 예측한 결과를 훈련 데이터에 추가하면 성능 향상에 도움 됨
- Voting Classifier 쓸 때 다양한 모델을 쓰는 것보다 적절한 모델을 쓰는게 좋음
