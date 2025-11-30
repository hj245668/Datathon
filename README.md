[ M Therapy ] 

Mental Health Risk Prediction & Intervention Effect Simulation  
**Mental Health Datathon – Final Submission**

본 프로젝트는 학생·직장인의 정신건강 위험도를 예측하고,  
세 가지 정책 개입 시나리오를 적용했을 때 우울 위험도 감소 효과(Protection Effect) 를 
정량적으로 분석한 모델 기반 접근입니다.

---

 1. Problem Definition

최근 청년층 정신건강 악화가 사회·기업의 핵심 문제로 대두되고 있습니다.  
특히 "재정 스트레스, 학업·업무 압박, 수면 부족"은 주요 위험 요인으로 알려져 있습니다.

DS6기 데이터톤에서는 다음 질문에 답하고자 합니다:

“특정 정책 개입이 실제로 정신건강 위험도를 얼마나 줄이는가?” 
→ 개입 시나리오별 **우울 확률 감소율(Protection Effect)** 정량화

---

2. Project Pipeline

 1) 데이터 탐색(EDA)
- Depression Rate Distribution  
- 학생 vs 직장인 우울 비율  
- Financial Stress / Sleep Duration / Academic Pressure 등 주요 Feature의 영향 분석  
→ 발표용 그래프 자동 생성 (fig1 ~ fig4)

 2) 예측 모델링 (XGBoost)
- 전처리: 결측치 처리 + 원핫인코딩  
- 클래스 불균형 보정(scale_pos_weight)  
- 검증 성능  
  - Accuracy  
  - Recall / Precision  
  - ROC-AUC  
- Confusion Matrix 자동 생성 (fig5)

 3) 정책 개입 시나리오 정의
    
| Scenario           | 조정 Feature                                     | 설명 |
|---------           |--------------                                   |------|
| Financial Aid     | Financial Stress ↓ 30% (상위 30%)               | 장학·재정지원 정책 |
| Sleep Education   | Sleep Duration → “7–8 hours”                   | 수면교육 개입 |
| Stress Counseling | Academic Pressure ↓20%, Work/Study Hours ↓10% | 상담·스트레스완화 패키지 |

 4) 개입 후 우울 확률(W-score) 변화 계산
     
    각 시나리오 적용 후 모델 예측 확률(W)을 재산출

 5) 보호효과(Protection Effect, PE) 계산
    
  PE =  ((W_base - W_scenario)/ W_base )) * 100

 6) 결과 시각화
    
  - 시나리오별 보호효과 Bar Chart (fig6)  
  - 위험도 분포 변화(KDE Plot, fig7)  
  - 재정 스트레스 타겟팅 그룹별 보호효과 비교(fig8)

---

3. Key Findings
   
 모델이 발견한 주요 위험 요인

- Financial Stress (가장 강력한 영향력)
- Sleep Duration
- Academic Pressure
- Work/Study Hours

4. Protection Effect (전체 학생 기준)

| 개입 시나리오 | 위험도 감소율(PE) |
|---------------|------------------|
| **Financial Aid (재정 지원)** | **12.7% ↓** |
| Stress Counseling (상담·스트레스 완화) | 4.3% ↓ |
| Sleep Education (수면 교육) | 3.0% ↓ |

➡ 특히 **재정 스트레스 상위 30% 집단**에서 PE가 가장 크게 나타남.

---

5. How to Run (Colab / Local)

  ✔ Requirements  : 
        pandas 
        numpy
        scikit-learn
        matplotlib
        seaborn
        xgboost

     ✔ Run on Google Colab
        1. `datathon_Mtherapy_final.ipynb` 업로드
        2. `train.csv`, `test.csv` 업로드
        3. `런타임 → 모두 실행`
        4. 다음 파일들이 자동 생성됨:
             - `fig1_target_dist.png`  
             - `fig2_student_worker.png`  
             - `fig3_financial_stress_dep.png`  
             - `fig4_sleep_dep_stacked.png`  
             - `fig5_confusion_matrix.png`  
             - `fig6_protection_effect.png`  
             - `fig7_risk_dist_base_vs_fs.png`  
             - `fig8_pe_by_group_fs.png`  
             - `submission_example.csv`
             
  6. File Structure

        MTherapy/
            │── datathon_Mtherapy_final.ipynb
            │── train.csv
            │── test.csv
            │── submission_example.csv
            │── fig1_target_dist.png
            │── fig2_student_worker.png
            │── fig3_financial_stress_dep.png
            │── fig4_sleep_dep_stacked.png
            │── fig5_confusion_matrix.png
            │── fig6_protection_effect.png
            │── fig7_risk_dist_base_vs_fs.png
            │── fig8_pe_by_group_fs.png
            └── README.md (현재 파일)
  7. Conclusion

  본 프로젝트는 [정책 개입에 따른 우울 위험도 감소 효과를 정량적으로 분석]하여  
  사회·교육·기업 영역에서 실제 적용 가능한 인사이트를 제시하고자 하였습니다.
  
  특히,
         “재정 스트레스 상위 집단 타겟팅”이 가장 높은 효율  
        ML 기반 위험도 예측 + 정책효과 시뮬레이션으로 의사결정 지원 가능

---
본 분석은 모두연구소 DS6기 Datathon 참가 목적으로 작성되었습니다.
Mental Health Datathon에서 제공된 데이터셋을 기반으로 수행하였으며,
진행기간 2025.11.26 ~ 28 약 3일간 M Therapy team 이 함께 하였습니다.
M therapy team : 혜영님, 기화님, 성현님, 현진님
