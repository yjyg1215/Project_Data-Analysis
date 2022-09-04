# ❓다음 분기에 어떤 게임을 설계해야 할까?
데이터셋 - Kaggle Video Game Sales
- Rank - Ranking of overall sales
- Name - The games name
- Platform - Platform of the games release (i.e. PC,PS4, etc.)
- Year - Year of the game's release
- Genre - Genre of the game
- Publisher - Publisher of the game
- NA_Sales - Sales in North America (in millions)
- EU_Sales - Sales in Europe (in millions)
- JP_Sales - Sales in Japan (in millions)
- Other_Sales - Sales in the rest of the world (in millions)
- Total_Sales - Total worldwide sales. → (new feature)
--------------------------------------------
## *데이터 전처리*
- 중복치 제거
- 결측치 확인 -> 결측치가 전체 데이터의 약 2%에 불과해서 제거 처리 진행.
- Year
  - 두자리수(ex. 1977->77, 2010->10) 데이터를 네자리수 포맷으로 통일.
  - 데이터 타입 Float에서 Int로 변경.
- Sales
  - 'K', 'M' 이라는 문자가 포함된 값은 [K=0.001, M=제거] 처리 진행.
  - 데이터 타입 Object에서 Float로 변경.
- Total_Sales라는 새로운 feature 생성.
---------------------------------------
## *데이터 분석*
1. 지역에 따라서 선호하는 게임 장르가 다를까?
    - 가설 검정 -> 카이제곱 독립성 검정 진행.
    - 지역마다 장르별 게임 출고량 시각화
2. 연도별 게임 트렌드가 있을까?
    - 연도와 플랫폼 -> 플랫폼별 게임 출고량을 시간의 흐름에 따라 시각화
    - 연도와 장르 -> 장르별 게임 출고량을 시간의 흐름에 따라 시각화
3. 출고량이 높은 게임에 대한 분석 및 시각화 프로세스
    - 출고량 상위 30개의 게임에 대해서 분석
      - 게임회사 -> 지역마다 게임회사별로 얼마나 비율을 차지하는지 시각화
      - 장르 -> 지역마다 장르별로 얼마나 비율을 차지하는지 시각화
      - 플랫폼 -> 지역마다 플랫폼별로 얼마나 비율을 차지하는지 시각화
4. 닌텐도 플랫폼 게임과 플레이스테이션 플랫폼 게임은 각각 어떤 장르가 인기가 많을까?
    - 닌텐도의 플랫폼에서의 장르별 게임 출고량 시각화
    - 플레이스테이션의 플랫폼에서의 장르별 게임 출고량 시각화
 --------------------------------------------------------
## *결론 및 출고량 예측*
  - PlayStation의 가장 최근에 출시된 플랫폼에서 Action 장르의 게임을 출시한다.
  - 출고량 예측 -> 경사하강법
-------------------------------------------------------
`EDA` `Feature Engineering` `Data Manipulation` `Data Visualization` `Hypothesis Test` `Gradient Descent`
