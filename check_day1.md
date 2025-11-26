1) 주요 변수 인사이트 메모 (간단 템플릿)

파일명: Day1_Key_Variable_Insights.md

주요 변수 인사이트 (Day 1)
1. 타깃(Depression) 기본 특성 요약

Dep=0: ___%

Dep=1: ___%

클래스 불균형 여부: ___

2. 핵심 수치형 변수 요약

Work_Pressure

Dep=1 평균: ___

Dep=0 평균: ___

핵심 메모: ___________________________

Sleep_Duration

Dep=1 평균: ___

Dep=0 평균: ___

핵심 메모: ___________________________

Job_Satisfaction

Dep=1 평균: ___

Dep=0 평균: ___

핵심 메모: ___________________________

(필요 시 한두 개 더 추가)

3. 핵심 범주형 변수 요약

City

Dep 비율 높은 도시: ___

메모: ___________________________

Family_History

Dep=1 비율: ___

메모: ___________________________

4. Day 1 기준 인사이트 5줄 요약
2) Baseline 모델 결과표 (간단 템플릿)

파일명: Day1_Baseline_Results.md

Baseline Model 비교표
모델	Accuracy	ROC-AUC	Precision	Recall	F1	메모
Logistic Regression	___	___	___	___	___	
RandomForest	___	___	___	___	___	
(옵션) XGBoost	___	___	___	___	___	
모델링 환경 메모

전처리: One-Hot + Standard Scaling

데이터 분리: train/test or K-Fold

Seed: 42

Day 1 결론

가장 나은 모델: ______

Day 2에서 개선할 포인트:

3) 1차 가설 리스트 (간단 템플릿)

파일명: Hypothesis_Day1.md

1차 가설 리스트 (Day 1)
가설 1

업무 압박(Work_Pressure)이 높을수록 Dep 확률이 증가한다.
근거: EDA 평균 차이, Feature Importance 상위.

가설 2

수면시간(Sleep_Duration)이 짧을수록 Dep 위험이 증가한다.
근거: 수면 분포 차이 명확.

가설 3

조직 만족도(Job_Satisfaction)는 매우 강한 예측 변수다.
근거: Dep=1과 Dep=0의 평균 차이 큼.

가설 4

지원 체감(Support Level)은 보호 요인 역할을 한다.
근거: Support가 낮은 그룹의 Dep 비율 높음.

가설 5

가족력(Family_History)은 독립적 위험 요인이다.
근거: Dep=1 그룹에서 비율 높음.

(선택) 가설 6

도시 규모(City)는 단독 영향보다 다른 변수와 결합해 영향을 준다.

핵심 검증축 (Day 2로 넘길 핵심 변수)

Work_Pressure

Sleep_Duration

Job_Satisfaction

Support Level

Family_History

City
