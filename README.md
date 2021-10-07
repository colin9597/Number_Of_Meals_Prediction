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
- 한국토지주택공사(LH) [link](https://dacon.io/competitions/official/235743/data)
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
