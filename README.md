# K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-
2022년 k-인공지능 제조데이터 분석 경진대회 - 도금욕 설비 데이터를 이용한 품질 이상 탐지 및 진단

# 프로젝트 수행기간 : 2022.10.10 ~ 2022.10.21

# 분석 동기 :
* 도금은 품질관리가 매우 까다롭고 반도체 산업에서 제품의 수명을 늘려주는 핵심 산업으로 공정의 최적화가 중요함
* 중소기업의 스마트팩토리 수준을 높이기 위해 도금욕 공정의 효율적인 품질 예측 모델이 필요함

# 분석 목표 : 
* 도금욕 공정에서 발생하는 공정데이터와 품질데이터 간의 상관관계를 분석하고 주요 원인인자를 분석함
* 공정 요소들의 적정 범위를 정하여 품질 예측 모델을 생성함

# 도금이란?

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/029e0e14-3b9f-4645-aa85-c32591840633)

* 물건의 표면 상태를 개선 또는 내구성을 강화할 목적으로 다른 물질의 얇은 층으로 피복하는 작업

# 전기도금

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/b84ff7ab-c5f3-4349-9ae6-729ce779bd68)

* 도금욜 설비 데이터에서는 도금 중에서도 전기도금을 이용
* 전기도금이란 전착의 원리를 이용하여 제품의 표면에 금속의 피막을 부여
* 도금욕이란 도금액이 도금조 내에 들어 있는 상태를 의미하며 실제 도금이 진행되는 작업

# 도금의 문제

* 도금공정의 용액의 농도와 온도가 높을수록 화재•폭발 위험이 있음
* 도금공정에서 대량의 물이 사용되어 온도 조절이 어려움
* 전압•전류에 관련된 설비 조작이 체계적이지 않고 경험에 의존하여 진행되고 있음
* 공정설비와 관련된 다양한 데이터를 수집하고 있으나 활용하지 못하여 품질 관리에 어려움을 겪음
* > 해결 방안 : 도금 공정에서 발생하는 데이터를 기반으로 공정에서 발생하는 문제를 파악하고 공정 운영 최적화, 품질 예측 등에 품질 예측 모델을 적용

# EDA(1/6) - dataset preview

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/b36a9638-a4c8-4261-8cef-877daa7dda88)

* 도금욕 데이터셋은 결측치를 자동으로 채우고 있어 에러 데이터 셋이 따로 존재함
* 데이터 전처리 후 에러데이터와 병합이 필요함

# EDA(2/6) - data describe(1/2)

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/15488357-d6fc-47dd-bb0d-ea72b138ae5f)

* pH : 평균에 비해 매우 큰 값이 있음
* Temp : 평균에 비해 매우 낮은 값이 있음
* Current : 평균에 비해 매우 낮은 값이 있음
* Voltage : 평균에 비해 매우 낮은 값이 있음

# EDA(3/6) - data describe(2/2)

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/847b0990-82bf-4925-a481-2b6feffe2190)

# EDA(4/6) - Xdata preview

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/35d4c78d-baf6-42a0-80a4-f7dcdfdc1406)

* 앞의 데이터를 전처리 후 에러데이터와 병합
* Xdata를 이용하여 Train data와 Test data를 분리(test : train - 8:2)

# EDA(5/6) - Xdata describe(1/2)

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/3871f6ec-d0bf-4b0a-9e2f-70840b0adc10)

* Xdata 이전 데이터와 에러 데이터를 병합하여 모델 학습에 적합하도록 데이터를 생성
* Current : 평균에 비해 큰 값이 있음
* pH : 평균에 비해 매우 큰 값이 있음
* Temp : 평균에 비해 매우 큰 값, 작은 값이 있음
* Voltage : 평균에 비해 매우 낮은 값이 있음

# EDA(6/6) - Xdata describe(2/2)

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/45b58a15-d3cb-4d8b-b7c3-973a0f5216a9)

* Correlation
* pH - Current
* pH – Voltage
* > 선형적인 상관관계는 보이지 않음

# Modeling(1/3)

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/6a8bfe6d-0cd4-4128-a590-4405311aea43)

# Modeling(2/3)

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/62c5840e-2788-4548-94f0-51a62341d077)

# Modeling(3/3)

![image](https://github.com/shinho123/K-Artificial-Intelligence-Electronic-Manufacturing-Data-Analysis-Competition-plating-process-/assets/105840783/c33ffbd8-0740-47e0-91eb-7bdc7ce89c37)

# Conclusion

* 본 프로젝트에서는 중소기업의 스마트팩토리 수준을 높이고 도금욕 공정의 효율적인 품질 예측을 위해 다음과 같은 분석 목표를 가짐
* 도금욕 공정에서 발생하는 공정데이터와 품질데이터 간의 상관관계를 분석하고 주요 원인 인자를 분석
* 공정 요소들의 적정 범위를 정하여 품질 예측 모델을 생성 후 성능 검증
* Modeling : 머신러닝 (DecisionTree, RandomForest, XGBoost)과 Autokeras 모델을 구현하고 ConfusionMatrix, ROC curve 로 성능을 평가한 결과, 분류 성능이 모두 우수함
* Tree 기반의 머신러닝 모델의 VI를 통해 총 2개의 변수가 양/불량품 예측에 있어 중요한 변수로 도출되었음
  - pH (전해액의 pH농도)
  - Voltage (전압 측정값)
* 도금공정은 다양한 분야에서 사용되기 때문에 해당 데이터셋의 모델을 조금만 변형하면 다양한 공정에서도 품질 관리를 쉽게 할 수 있음
