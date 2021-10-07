# <Number_Of_Meals_Prediction>
[DACON] 구내 식당 식수 인원 예측 AI 경진대회 (2021.09)  
- 개인 프로젝트  
- PNU 데이터톤 2021 최우수상
---
## 개발 환경
#### [개발 환경]
- 서버 : Colab
- CPU 2.20GHz 2코어
- 메모리 12GiB
- CUDA 11.2
- Ubuntu 18.04.5 LTS
- Python 3.7.11

#### [데이터 출처]
- 한국토지주택공사(LH) 제공 [link](https://dacon.io/competitions/official/235743/data)
---

## Data
#### [train.csv]
- 중식계, 석식계(식수 인원) 포함
- train.shape : (1205, 12)

#### [test.csv]
- 중식계, 석식계(식수 인원) 미포함
- test.shape : (50, 10)

#### [sample_submission.csv]
- sample_submission.shape : (50, 3)
---

## Preprocessing & EDA
- 분석 내용은 마크다운으로 코드에 정리
#### [산점도 분석]
![산점도](https://user-images.githubusercontent.com/80561963/136307474-029e99ff-d6cf-4a93-aea2-c36a8a6a768e.png) 

#### [상관분석]
![상관](https://user-images.githubusercontent.com/80561963/136307622-96f401dd-a46f-44ca-87c7-711616d00ae6.png)

#### [요일별 식수인원]
![요일별](https://user-images.githubusercontent.com/80561963/136308025-04d0d14d-116f-4b5b-9682-e3b97ede8e30.JPG)

#### [날짜별 식수인원]
###### 1) 연도별 식수인원
![연도별](https://user-images.githubusercontent.com/80561963/136308746-0a9c8173-1017-47f4-93f2-eac5e25658e9.JPG)

###### 2) 월별 식수인원
![월별](https://user-images.githubusercontent.com/80561963/136308733-79a21305-dd0d-4aff-a129-a928ffa460e9.JPG)

###### 3) 연월별 식수인원
![연월별](https://user-images.githubusercontent.com/80561963/136308752-b85bce0b-eb9a-4517-b0fc-4ea44d023f24.JPG)

#### [파생변수 생성]
###### 1) 현재 본사에 있는 잔류 인원
- 'present' = '본사정원수' - '본사휴가자수' - '본사출장자수' - '현본사소속재택근무자수'

###### 2) 날짜
- '일자' 변수를 datetime형으로 변환 후, 요일, 'year', 'month', 'day'를 각각 생성

###### 3) 날씨
- 기상청 사이트에서 날씨 데이터를 수집
- 기온 데이터(temperature.csv)의 결측치는 보간법으로 처리하고 'avg_temp', 'high_temp', 'low_temp' 파생변수 생성
- 강수량 데이터(rainfall.csv)의 결측치는 '0'으로 처리하고 'rainfall' 파생변수 생성

###### 4) 메뉴 정리
