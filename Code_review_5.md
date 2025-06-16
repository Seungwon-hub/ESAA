## 주제 및 데이터

### 주제

- 은행 고객의 이탈 여부를 예측하는 AI 알고리즘

### About data

- **train.csv [파일]**
    - 은행 고객 관련 정보
    - ID : 샘플 별 고유 ID
    - Exited : 이탈 여부 ( 예측 목표 )

### 코드 리뷰

1. **EDA**
- 결측치 확인
- 상위 5개 행 확인
- 타겟 분포 확인
- 상관관계 분석
- 히트맵 시각화
- 국가별 이탈 여부
- 이탈 여부
1. **Preprocessing**
- 불필요한 변수 제거
- LabelEncoder 통해 범주형 변수 인코딩
- StandardScaler로 수치형 변수 스케일링
- 타겟 불균형 위해 SMOTE 오버샘플링
1. **Modeling**
- 모델: xgb, lgbm, catboost
- Stacking meta model: Logistic Regression
- 교차 검증 및 모델 학습: Stratified K-Fold, acc, f1-score

### 차별 점 및 배울 점

- SMOTE 사용하여 데이터 불균형을 효과적으로 해결
- Stratified K-fold로 타겟 분포를 유지한 교차 검증 수행
- 각 모델별로 하이퍼파라미터 튜닝을 통해 최적의 모델 학습 진행
