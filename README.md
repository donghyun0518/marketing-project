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
   - 중국발 C커머스의 등장으로 인한 이커머스 시장 경쟁 심화로 국내 이커머스 기업들의 가격 경쟁력이 약화

**2. **데이터 수집 및 전처리****
   - 데이터 출처 : DACON 이커머스 고객 세분화 분석 아이디어 경진대회
   - 전처리 작업
     - 군집 분석과 세분화 분석을 위한 파생변수 생성

**3. **군집 분석 모델 선정****
   - 모델 선정 : K-Means, MCLP, OPTICS
   - 모델 적용 분석 과정
     - 총 14개 행정동에 대해 입지 선정 분석 진행.
     - K-Means 군집 분석을 하기 위한 변수 선정( 버스정류장 / 횡단보도 위치 / 버스 정류장별 노선 수 / 주차장 )
     - K-Means 군집 결과를 기반으로 K 값을 선정하여 MCLP 기법 적용. 최대한 많은 수요를 커버할 수 있는 최적의 위치를 선정
     - MCLP 기법을 적용한 후 평가기준에 만족하지 못하는 행정동에 대해서 OPTICS 기법을 적용하여 입지를 선정.
   - **평가 지표**
     - K-Means : Elbow Method(엘보우 기법), Silhouette Score(실루엣 점수)
       - 공공 전기자전거 거치대 수를 각 동의 지역적 특성에 맞는 최적의 수를 반영하기 위해 각 행정동의 어울링 거치대 수를 K값으로 설정.
       - 실루엣 점수가 0.5이상인 지점을 K값으로 설정.
       - 0.5이하라면 지정한 K값에서 0.5이상으로 도달한 가장 가까운 지점을 K값으로 설정.
     - MCLP : Coverage ratio(커버리지 비율)
       - 실루엣 점수가 0.5이상이면서 커버리지 비율이 0.7이상인 행정동 선정
     - OPTICS : Silhouette Score(실루엣 점수)
       - 앞선 모델들의 평가 기준을 만족하지 못하는 행정동에 대해서 OPTICS 모델을 적용.
       - 나머지 행정동의 실루엣 점수가 0.5를 넘기는 것을 확인.

**4. **분석 결과****
   - 총 8개의 행정동에 대해 MCLP 모델을 적용.
   - 총 6개의 행정동에 대해 OPTICS 모델을 적용.
   - 위 두 모델을 적용하여 공공전기자전거 거치대 최적 입지를 선정.

**5. **기대 효과****
   - 세종시 교통 체증 완화
   - 세종시가 차 없는 도시라는 이미지에 더 가까워질 수 있음.
   - 궁극적으로 세종시 시민의 삶의 질 향상을 기대할 수 있음.


## 🧑🏻‍💻환경
- Python
- VScode

