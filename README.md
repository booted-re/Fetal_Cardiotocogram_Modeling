# Codestates AI Bootcamp Project
# Fetal Cardiotocogram Analysis Modeling
# 태아 초음파검사 분석 모델링

## 문제 정의
* 많은 태아/산모의 사망이 의료 환경이 뒷받침되지 못하는 상황에서 적절한 치료 없이 발생하고 있다.
* 전 세계적으로 295,000건 (2017년)
* 초음파검사(Cardiotocograms, CTGs)는 산모/태아를 위한 가장 접근성이 높은 진단 수단 중 하나다.
* 진단 데이터를 머신 러닝을 통한 모델링으로 높은 정확도의 분류가 가능하다면, 의료 자원의 사용을 최적화할 수 있다.

## ML Pipeline
1. 모델링**
* XGBoost Classifier

2. 모델 최적화**
* Permutation Importance를 이용해 Feature를 선택함
* Cross-Validation 방법을 통해 하이퍼파라미터 최적화

3. CV Hyperparameter Tuning

## 결과
* Baseline 모델에 비해 상당히 향상된 예측 결과가 나타났다.
* 그러나 False Label(추가 진단 필요)의 진단 정확성이 그다지 높지 않다.
실제 문제가 있는 경우를 정확하게 진단하는 것이 더 중요하다.
* 모델이 아래의 3가지 특성을 중점적으로 활용하여 예측한 것으로 보인다. 그러나 중요도가 낮은 데이터를 삭제했을 때 모델의 예측이 부정확해지므로 feature와 target 간 추가적인 분석이 필요하다.
1. abnormal_short_term_variability
2. accelerations
3. mean_value_of_short_term_variability
* 데이터셋은 2,000여개의 표본으로 더 많은 데이터를 통한 추가적인 학습과 모델 개선이 필요하다.

## 사용 데이터셋
*Ayres de Campos et al.* (2000) SisPorto 2.0 A Program for Automated Analysis of Cardiotocograms. J Matern Fetal Med 5:311-318
