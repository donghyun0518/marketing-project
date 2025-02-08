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
   - **Min-Max 정규화** : 데이터의 최소값을 0, 최대값을 1로 스케일링하여 모든 데이터가 동일한 범위 내에 위치하도록 조정하여 서로 다른 스케일을 가진 데이터를 모델에 적용하기 쉽게 만듦.
    
   - **주성분 분석(PCA)** : 데이터에 포함된 변수가 많아질수록 분석이나 모델링의 복잡도가 기하급수적으로 증가하기 때문에 차원의 저주에 빠지는 것을 방지하기 위한 기법.
     - 데이터의 특성을 최대한 유지하면서 저차원을 축소하여 모델링의 복잡도를 완화함.
     
     - **최종 모델에서 변수는 4개이지만 PCA를 적용한 이유**
       - 변수 조합을 찾기 위해 모든 변수를 넣어서 모델을 생성하여 초기 모델에서 차원의 저주를 방지하기 위해 PCA를 적용하여 변수 조합을 찾았기 때문에 모델의 재현성을 유지시키기 위해서 최종 모델에서도 PCA 기법을 적용하여 모델을 생성하였음.

**6. 군집 분석 결과**
   - K-Means의 실루엣 점수가 0.581로 가장 높은 군집력을 보여 K-Means 모델을 채택.
   - 각 클러스터 별로 군집 특성에 대해 고객 분류 및 마케팅 전략
     - Cluster 0 : 저가 + 대량 구매형 고객 / 품목 고급화 유도, 추가 구매 유도, 대량 구매시 할인
     - Cluster 1 : 저가 + 쿠폰 민감형 고객 / 구매가 몰려있는 카테고리 위주로 소액 쿠폰 제공, 쿠폰 제공 시 동일 카테고리 내 중가 이상의 가걱대 상품 추천, 번들 세일
     - Cluster 2 : 중저가 + 할인율 민감형 고객 / 구매가 많은 요일에 타임 세일, 평균 단가보다 높은 금액대 제품 한정 고할인율 쿠폰을 제공해 평균 단가를 높이는 전략
     - Cluster 3 : 고가 + 쿠폰 둔감형 고객 / 고가 상품 수요에 부응하는 프리미엄관 운영
   - 군집별 특성을 분석하여 맞춤형 전략을 세웠지만 매출의 53.3%를 차지하고 고객당 평균 매출이 타 클러스터에 비해 최대 135% 높은 Cluster 0 에 대해 추가 세분화 분석과 고객 맞춤형 전략의 필요성을 느낌.

**7. RMFV 분석 (2차 세분화)**
   - Recency : 언제 마지막으로 구입했는지
   - Frequency : 구매 빈도는 어느 정도인지
   - Monetary : 구매 금액은 얼마인지
   - Variety : 얼마나 다양한 카테고리를 구입했는지
   - 데이터의 각 컬럼별 데이터 값을 기준으로 5분위수를 적용. 각 분위수에 따라 1 ~ 5점의 점수를 부여함. 3점 이상이면 U(Up), 3점미만이면 D(Down)로 분류해 UUUU부터 DDDD까지 총 16개 조합으로 고객 2차 세분화 진행.
   - Cluster 0 내부에서 많이 차지하는 상위 5개의 고객군에 대해 마케팅 전략 도출
     - UUUU : 거래 횟수가 많은 수, 금요일에 일정 수요가 있으면서 평균 단가가 비싼 카테고리에 해당하는 쿠폰을 제공
     - UDDD : 과도한 마케팅 압박을 줄이고 긍정적인 사용자 경험을 제공하기 위해 3사분위수인 22일을 이용. 마지막 구매일로부터 22일이 넘어가는 시점에 리마인드 메세지 혹은 앱푸쉬 알림
     - DUUU : 구매가 많았던 카테고리 위주로 웰컴백 쿠폰 제공, 개인화된 메세지 발송
     - UUUD : 인기 카테고리인 Nest-USA와 함께 자주 구매된 다른 카테고리 상품을 추천
     - DDDD : 거래가 많았던 상품을 아ㅏㄹ고리즘에 노출 혹은 추천 메세지 발송

**8. 테블로 대시보드 제작**
[대시보드 확인 링크](https://public.tableau.com/app/profile/.30606921/viz/_17373700099870/34?publish=yes)


## 🧑🏻‍💻환경
- Python
- VScode

