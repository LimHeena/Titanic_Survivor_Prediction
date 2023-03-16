# 타이타닉 생존자 예측

### # 데이터 전처리

#### 1. 결측치 처리
- train, test 데이터에서 Cabin은 결측치 값이 너무 방대하여 처리에서 제외
- train, test에서 Age 처리 (이름의 이니셜을 추출해(ex.Mr) 각 이니셜별 나이 평균을 구하여 처리)
- train에서 Embarked 처리(2개 뿐이라 최빈값으로)
- test에서 Fare 처리(평균으로) (범주형으로 바꾸어 데이터를 다뤘으면 좋았을 것 같음)

#### 2. Sibsp, Parch를 가족수로 통합 -> 이후 원래 컬럼들 삭제

#### 3. Scaler
- StandardScaler로 수치형 데이터 처리

#### 4. 범주형 변수 처리
- 성별(LabelEncoder)
- 승선항(OneHotEncoder)

### # 모델링
- 로지스틱 회귀
- 의사결정 나무(criterion = 'entropy', max_depth = 1, random_state = 0)
- 랜덤 포레스트(n_estimators = 8, random_state = 0)
- XGBoost
- 그래디언트 부스팅(max_depth=1)
#### --> 데이콘에서는 그래디언트 부스팅의 점수가 제일 높았다. 

### 보완할 점
1. Cabin 결측치 처리
2. Fare 범주형으로 처리
+ 다양한 모델과 파라미터 스코어 점수 꼼꼼히 기록하기
+ 구글링에 너무 의존하지 않고 혼자 생각해보기
+ 피쳐별로 상관계수 파악해서 엮어보기
+ 배운 내용들 학습 위해 적용 많이 해보기(점수보다는 학습을 위할 때)
