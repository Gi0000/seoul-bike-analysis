# 서울시 공공자전거 이용 패턴 분석

## 프로젝트 목적
서울시 따릉이 이용량에 영향을 주는 요인과 대여소별 특성 분석

## 핵심 질문
- 출퇴근 시간과 주말의 이용 패턴은 어떻게 다를까?
- 어떤 대여소가 가장 많이 이용될까?
- 대여량이 많은 대여소와 반납량이 많은 대여소는 다를까?
- 비가 오거나 기온이 높아지면 이용량은 어떻게 달라질까?
- 대여소의 위치에 따라 서로 다른 이용 패턴이 나타날까?
- 과거 데이터를 이용해 다음 날 이용량을 어느 정도 예측할 수 있을까?

## 이 프로젝트에서 연습할 기술
| 분야 | 파이썬 기술 | 난이도 |
| --- | --- | --- |
| 데이터 수집 | CSV, 파일 입출력, `pathlib` | 쉬움 |
| 데이터 가공 | `pandas`, `numpy` | 보통 |
| 데이터 정제 | 결측치, 중복, 이상치, 자료형 변환 | 보통 |
| 통계 분석 | `groupby`, `pivot_table`, 상관관계 | 보통 |
| 시계열 분석 | `datetime`, `resample`, `rolling` | 보통 |
| 데이터 결합 | `merge`, `join` | 보통 |
| 시각화 | `matplotlib`, `seaborn` | 보통 |
| 공간 분석 | `folium`, 좌표 데이터 | 보통~어려움 |
| 예측 모델 | `scikit-learn` | 어려움 |
| 코드 구조화 | 함수, 모듈, 예외 처리 | 보통 |


## 데이터 출처
1. 서울시 따릉이 대여이력   
    https://data.seoul.go.kr/dataList/OA-15182/F/1/datasetView.do?utm_source=chatgpt.com  
    개별 자전거의 대여·반납 기록을 분석하는 핵심 데이터. 우선 2025년 중 한 달만 사용하고, 나중에 분석 범위를 확대.
2. 서울시 공공자전거 대여소 정보(2단계 데이터)  
    https://data.seoul.go.kr/dataList/OA-13252/A/1/datasetView.do?utm_source=chatgpt.com  
    대여소 이름, 관리번호, 위도·경도 등의 정보를 이용해 위치 분석과 지도 시각화를 진행.
3. 기상청 종관기상관측(ASOS, 3단계 데이터)  
    https://data.kma.go.kr/data/grnd/selectAsosRltmList.do?pgmNo=36&utm_source=chatgpt.com  
    기온, 강수량, 습도 등 날씨 데이터를 결합해 날씨가 따릉이 이용량과 어떤 관계가 있는지 분석