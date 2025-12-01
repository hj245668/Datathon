MTherapy
Mental Health Risk Prediction & Intervention Effect Simulation
DS6 Mental Health Datathon – Final Submission

본 프로젝트는 학생 정신건강 위험도 예측 모델을 구축하고,
여러 정책 개입 시나리오를 적용했을 때 실제 우울 위험도가 얼마나 감소하는지
'보호효과(Protection Effect)'를 정량적으로 산출하는 것을 목표로 한다.

Dataset: 인도 학생 정신건강 설문 (DS6 Datathon 제공)
Period: 2025.11.26 ~ 2025.11.28 (3일)
Team: M Therapy (혜영 · 기화 · 성현 · 현진)

---

 1. Problem Definition

청소년 정신건강 문제는 인도뿐 아니라 전세계적 사회위험요인으로 부상하고 있다.
본 데이터톤에서는 다음 질문을 해결하고자 했다:

“특정 정책 개입이 실제로 학생의 우울 위험도를 낮추는가?”

→ 단순 관찰이 아니라 모델 기반 시뮬레이션으로 효과를 검증.

---

2. Project Pipeline

 1) 데이터 탐색(EDA)
- 우울증 비율(전체/학생/직장인 비교)
- Feature 영향도: Financial Stress, Sleep Duration, Academic Pressure 등    
→ 시각화 생성 

 2) 예측 모델링 (XGBoost)
- 전처리: 결측치 처리, 범주형 원핫 인코딩
- 불균형 보정 : scale_pos_weight  
- 검증 성능  
  - Accuracy  
  - Precision  
  - Recall   
- Confusion Matrix, Feature Importance 생성

 3) 정책 개입 시나리오 정의 (학생 중심)
    
Scenario	           적용 Feature 변화	                            정책 목적
Stress Reduction	   Academic/Work Pressure ↓30%, Financial ↓30%	  스트레스 완화
Sleep Improvement	  Sleep Duration → 7.5h	                        수면 습관 개선
Healthy Diet	       Dietary Habits → Healthy = 1	                 영양 개선
Work-Life Balance   Work/Study Hours ↓20%	                        학업부담 완화
Satisfaction Boost	 Satisfaction +20%	                            심리적 만족 증가
Comprehensive	      위 5가지 정책 모두 적용	                       종합 개입

 4) 개입 후 위험도 재산출
     
    모델에 시나리오별 입력값을 넣고 예측 확률 비교

 5) 보호효과(Protection Effect, PE) 계산
    
  PE =  ((W_base - W_scenario)/ W_base )) * 100

 6) 결과 시각화
    
  - 시나리오별 보호효과 Bar Chart  
  - Student High-risk Group 효과 비교

---

3. Key Findings (학생 모델 기준)
   
 모델이 발견한 주요 위험 요인

- Financial Stress (가장 강력한 영향력)
- Sleep Duration
- Academic Pressure
- Work/Study Hours

4. Protection Effect (전체 학생 기준)

시나리오	            위험도 감소율(PE)	    해석
Comprehensive	       34.8% ↓	              가장 효과 높음
Stress Reduction	    27.2% ↓	              단일개입 중 최강
Healthy Diet	        7.8% ↓	               보조 수준
Work-Life Balance	   3.1% ↓	               단독효과 낮음
Satisfaction Boost	  0%	                   영향 없음
Sleep Improvement	   -1.6% (악화)	         단독으로는 반효과

---

5. How to Run (Colab / Local)

  ✔ Requirements  : 
        pandas 
        numpy
        scikit-learn
        matplotlib
        seaborn
        xgboost

   ✔ Run on Google Colab / Local
        1. `Mtherapy_v1.ipynb` 업로드
        2. `train.csv`, `test.csv` 업로드
        3. `Mtherapy_v1_simulation_PE.ipynb` 업로드
        4. `Mtherapy_DataAnalysis.ipynb` 업로드
        5. `런타임 → 모두 실행`
             
  6. File Structure

        MTherapy/
            │── Mtherapy_v1.ipynb
            │── train.csv
            │── test.csv
            │── Mtherapy_v1_simulation_PE.ipynb
            │── Mtherapy_DataAnalysis.ipynb
            │── 발표자료_Mtherapy_v1.png
            └── README.md (현재 파일)
     
  8. Conclusion

  본 프로젝트는 단순 예측을 넘어 정책 개입에 따른 위험도 변화까지 시뮬레이션함으로써
  실제 교육행정·사회정책에서 활용 가능한 근거 기반 모델링을 제공하였다.
  
  특히,
         “고위험군 타겟팅 + 스트레스 완화 패키지”가 가장 강력한 효과
         종합개입 시 정책효율이 2–3배 상승
         ML 기반 정책효과 분석은 향후 정교한 의사결정에 필수
         
---
본 분석은 모두연구소 DS6기 Datathon 참가 목적으로 작성되었습니다.
Mental Health Datathon에서 제공된 데이터셋을 기반으로 수행하였으며,
진행기간 2025.11.26 ~ 28 약 3일간 M Therapy team 이 함께 하였습니다.
M therapy team : 혜영님, 기화님, 성현님, 현진님
