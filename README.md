# 제주도 교통 안전 취약 초등학교 검토

## 📌 개요

**분석 배경**

제주도에서 스쿨존 교통사고 예방에 관한 정책을 시행하고 있으나 스쿨존 어린이 교통사고 건수가 줄어들지 않는 문제 발생 <br/>

**분석 목표**

초등학교 스쿨존 교통 안전 환경을 세분화한 후 주요 취약점을 파악하여 효과적인 스쿨존 교통사고 예방 정책 수립 제안 <br/>

## 📌 분석 과정

1. 데이터 수집 및 전처리
- 어린이 사고 발생 지점의 위경도를 웹크롤링으로 수집하여 어린이 사고 발생 지점의 행정동 추출
- 어린이 사고가 가장 많이 발생했던 상위 10개의 행정동을 분석 대상으로 지정
- 분석 대상 행정동에 속한 초등학교들의 스쿨존 교통 안전 환경 요인 데이터 수집 및 취합 <br/>

2. EDA
- 행정동 별 인구 특성 및 스쿨존 안전 환경 요인 관련 EDA 및 시각화 <br/>

3. 클러스터링
- K-means 기법을 이용하여 스쿨존 교통 안전 환경의 특징이 유사한 초등학교 그룹으로 분류
- 각 그룹 별 스쿨존 교통 안전 환경 특징 파악 <br/>

4. 요인분석
- 각 초등학교의 스쿨존 교통 안전 환경 관련 설문조사 데이터에 요인분석을 적용해 설문조사 항목들을 공통된 요인으로 정의
- 요인에 속한 설문 항목들의 응답 결과를 계수화해 각 요인에 대한 초등학교의 위험도 지표를 산출 <br/>

5. ANOVA
- 각 요인에 클러스터 간 유의미한 위험도 지표 차이가 존재하는지 검토
- 초등학교 그룹 간 유의미한 차이가 존재하는 경우, Bonferroni t-test 사후 검정을 통해 어떤 클러스터에서 해당 요인에 대해 뚜렷한 차이를 보이는지 확인 <br/>

## 📌 분석 결과

1. K-means

- 실루엣 계수는 0.473이었으며 49개의 초등학교가 총 3개의 그룹으로 분류됨

2. 요인분석

- 15개의 설문 항목들을 5개의 요인으로 요약

- 요인1 : 학생들이 체감하는 스쿨존의 전반적인 사고 위험도, 요인2 : 차도 위 사고 위험도, 요인3 : 횡단 시 사고 위험도, 요인4 : 버스 이용 시 사고 위험도, 요인5 : 자전거 이용 시 사고 위험도 

3. ANOVA 검정

- 요인1(학생들이 체감하는 스쿨존의 전반적인 사고 위험도)은 그룹 간 유의미한 차이가 존재하지 않음

- 그룹 2는 요인3(횡단 시 사고 위험도)이 가장 높음

- 그룹 3은 요인2(차도 위 사고 위험도), 요인4(버스 이용 시 사고 위험도), 요인5(자전거 이용 시 사고 위험도)가 가장 높음

**결론**
| 그룹 | 스쿨존 교통 안전 환경 취약점 | 결론 | 해결방안 제안 |
| --- | --- | --- | --- |
| 그룹 1 | - 도로폭이 좁고 차로수가 적음 <br/>- 제주국제공항과 제주 유명 관광지에 위치
- 불법주정차 문제 | - 대중교통 이용과 유동인구가 많은 관광지 지역으로 횡단 시 사고 위험도가 높음 | - 스쿨존 내 불법 주정차 단속 강화 
- 스쿨존 내 안전 운전 유도 및 안내 장치 마련 |
| 그룹 2 | - 도로폭이 가장 넓고 차로수가 많음
- 교통 표지와 신호등 개수가 많음
- 횡단 시 사고 위험도가 상대적으로 가장 높음 | - 제주도민들이 거주하는 지역
- 교통량이 많고 도로가 넓어 횡단 시 사고 위험도가 높음 | - 등하교 시간 및 학생들이 자주 이동하는 시간대에 횡단 안전 도우미 운영
- 무단횡단 예방을 위한 중앙분리대 설치 |
| 그룹 3 | - 교통 표지 및 신호등 개수가 적음
- 보차분리비율이 낮음
- 차도 위 사고 위험도, 버스 이용 시 사고 위험도, 자전거 이용 시 사고 위험도가 상대적으로 가장 높음 | - 교통량은 적으나 차도와 인도의 경계가 모호함
- 전반적인 교통 안전 인프라가 부족 | - 안전한 보도 확보를 위한 경계턱, 가드레일 설치
- 학생들이 자주 이동하는 구역에 횡단보도 및 신호등 설치  |
