<h1 style="text-align: center;">🛒 이커머스 고객 세분화 분석 - 군집 분석과 RFMV를 이용한 초세분화 마케팅 전략</h1>
<hr>
<p style="text-align: center;">
    <a href="https://github.com/donghyun0518/marketing-project/blob/main/%EC%B5%9C%EC%A2%85_%EB%A7%88%EC%BC%80%ED%8C%85.pdf" target="_blank">
        <img src="https://github.com/donghyun0518/marketing-project/blob/main/%EB%A7%88%EC%BC%80%ED%8C%85%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%ED%91%9C%EC%A7%80.png" alt="Project Cover" style="width: 1000px; border: 1px solid #c9d1d9; border-radius: 8px;">
    </a>
</p>

[프로젝트 발표 자료](https://github.com/donghyun0518/marketing-project/blob/main/%EC%B5%9C%EC%A2%85_%EB%A7%88%EC%BC%80%ED%8C%85.pdf)

## 🔍 프로젝트 개요
- **목적** : 고객 가치와 행동 패턴의 세분화에 대응 필요성이 대두, 궁극적으로 고객 충성도를 높이고 지속 가능한 성장을 도모하는 것이 목표이다.
- **주제** : 이커머스 고객 세분화 분석 - 군집 분석과 RFMV를 이용한 초세분화 마케팅 전략
- **기간** : 2024.12.09 ~ 2025.01.17 (약 6주간)
- **팀 구성** : 5인

## ⚙️ 주요 수행 과정
**1. **문제 정의****
   - 중국발 C커머스의 등장으로 인한 이커머스 시장 경쟁 심화로 국내 이커머스 기업들의 가격 경쟁력이 약화.
   - 따라서 고객 충성도를 높이고, 지속 가능한 성장을 할 수 있는 분석이 필요하다고 생각함.

**2. **데이터 수집 및 전처리****
   - 데이터 출처 : DACON 이커머스 고객 세분화 분석 아이디어 경진대회
   - 데이터 설명 : 온라인 거래와 관련된 정보, 고객 정보, 할인 쿠폰 관련 정보, 세금 관련 정보, 마케팅 비용 관련 정보 등 총 5개의 파일로 이루어진 데이터셋
   - 전처리 작업
     - 군집 분석과 세분화 분석을 위한 파생변수 생성

**3. **EDA****
   - 요일별 구매 횟수, 쿠폰사용 비율, 월별 평균 할인율, 구매 평균 단가 등 고객 행동패턴을 알 수 있는 정보를 시각화하여 분석에 활용할 수 있는 형태로 제작
   - 파레토 분석, 코호트 분석 등을 통해 고객 구매 패턴 파악

**4. **파생변수 생성 및 변수 선택****
   - 평균할인율, 평일_거래, 주말_거래, Average_Unit_Price, 구매 카테고리 다양성 등 고객의 특성을 나타낼 수 있다고 생각되는 변수들을 데이터를 통해 생성
   - 파생변수의 모든 조합을 K-Medoids, Birch, K-Means 모델에 적용하여 실루엣 점수가 가장 높게 나온 변수 조합을 채택
   - **최종 변수 조합** : '평균할인율','Average_Unit_Price','Total_수량','쿠폰사용비율'
     - 2차 세분화 과정에서 RFM 지표를 사용할 예정이기 때문에 군집분석에 사용할 변수에서 제외.
**5. **군집 분석****
   - Min-Max 정규화 : 데이터의 최소값을 0, 최대값을 1로 스케일링하여 모든 데이터가 동일한 범위 내에 위치하도록 조정하여 서로 다른 스케일을 가진 데이터를 모델에 적용하기 쉽게 만듦.
    
   - 주성분 분석(PCA) : 데이터에 포함된 변수가 많아질수록 분석이나 모델링의 복잡도가 기하급수적으로 증가하기 때문에 차원의 저주에 빠지는 것을 방지하기 위한 기법.
     - 데이터의 특성을 최대한 유지하면서 저차원을 축소하여 모델링의 복잡도를 완화함.
     
     - 최종 모델에서 변수는 4개이지만 PCA를 적용한 이유
       - 변수 조합을 찾기 위해 모든 변수를 넣어서 모델을 생성하여 초기 모델에서 차원의 저주를 방지하기 위해 PCA를 적용하여 변수 조합을 찾았기 때문에 모델의 재현성을 유지시키기 위해서 최종 모델에서도 PCA 기법을 적용하여 모델을 생성하였음.
   - 

**5. **기대 효과****
   - 세종시 교통 체증 완화
   - 세종시가 차 없는 도시라는 이미지에 더 가까워질 수 있음.
   - 궁극적으로 세종시 시민의 삶의 질 향상을 기대할 수 있음.


## 🧑🏻‍💻환경
- Python
- VScode

