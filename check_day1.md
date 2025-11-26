Day 1
- Team building
- EDA, simple modeling - seeking best model
- insight confirm
  
1. EDA

1_1. target : Depression (특성 요약)
Dep=0: ___%
Dep=1: ___%
클래스 불균형 여부: ___

1_2. 핵심 수치형 변수 요약
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


1_3. 핵심 범주형 변수 요약

City
Dep 비율 높은 도시: ___
메모: ___________________________

Family_History
Dep=1 비율: ___
메모: ___________________________

2. modeling
 -  Baseline model 비교 
( 모델	Accuracy	ROC-AUC	Precision	Recall	F1	메모)
Logistic Regression	___	___	___	___	___	
RandomForest	___	___	___	___	___	
XGBoost	___	___	___	___	___

* 모델링 환경 description : 
전처리: One-Hot + Standard Scaling
데이터 분리: train/test or K-Fold
Seed: 42



3. Reflection 
Day 1 결론
                가장 나은 모델: ______

Day 2 에서 개선할 점

4. 가설 설정 (1차)
인사이트도출을 위한 가설 설정 

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
가설 6
        도시 규모(City)는 단독 영향보다 다른 변수와 결합해 영향을 준다.
        
5. 핵심 검증축 (Day 2로 넘길 핵심 변수)
   Work_Pressure
   Sleep_Duration
   Job_Satisfaction
   Support Level
   Family_History
   City

4. sharing
   강혜영
   이기화
   임성현
   소현진 ~ 혜열님의 직관적인 데이터 선택 및 공유 및 시작 코딩 공여로 스마트하게 시작할 수 있었습니다.
            기화님의 
            성현님의 
   
