# 🚗 부산시 음주운전 사고 예방과 단속 효율성 강화를 위한 DX 솔루션
![슬라이드1 JPG](https://github.com/user-attachments/assets/aff8f071-59dd-43f9-bdd6-835c7be5b1d5)

</br>

## 💡 프로젝트 소개
- KT Aivle School 6기 빅프로젝트
- 음주운전 사고에 관한 공공 데이터를 활용하여 음주운전 사고 예방과 경찰들의 단속 효율성을 높일 수 있는 DX 솔루션 제안
- 데이터 분석(상관관계 분석,K-means 군집 분석) & 머신러닝을 활용하여 음주운전 사고 발생 지역 분석 및 건수 예측
- 경찰이 사용할 수 있는 대시보드 및 모바일 앱 프로토타입까지 구현

</br>

## 팀원 구성

|역할|이름|깃허브|
|------|---|---|
|PM|김찬진|https://github.com/chaljin416|
|기술PM|노준영|https://github.com/junyoungnnn|
|UI/UX|김민영|https://github.com/min-young417|
|제안전략|이수빈|https://github.com/SuseongJr|
|데이터분석|류민주|https://github.com/Min8760|
|사업제안|김정훈|https://github.com/JungHoon1999|
|제안전략|류선우|https://github.com/Sunwoo0818|
|제안전략|오승욱|https://github.com/sehodo|

</br>

## 기획, 분석 Tool
- 협업 툴 : MS Teams, Notion, GitHub, Google Drive
- 디자인 및 프로토타입 : Figma
- 데이터 분석 : Python, Pandas, Sklearn, Keras, Matplotlib, Seaborn

</br>

## 1. 프로젝트 개요
현재 음주운전 단속 시스템은 과거 데이터를 기반으로 하여 불특정하게 단속을 이루어져 있으며 이는 효율적인 음주운전 단속이 이루어지고 있지 않다는 것으로 우리는 AI 데이터 분석을 통하여 고위험 지역을 예측하고 고위험지역 스마트 차량 차단기 실시 및 현장 단속으로 실시간 데이터를 수집하여 더욱 세분화된 위험 지역을 예측하고 효율적인 단속체계를 갖춘 시스템으로 바꾸고자 합니다.

</br>

## 2. 데이터 분석
### 사용 데이터
(사용 데이터 정리 후 추가 예정)

### 음주운전 발생에 영향을 미치는 중요도 높은 요인 선정
__가설)__ 부산광역시 구별 음식점, 주점, 버스 정류장 개수, 지하철역 개수, 지역구 별 인구수가 음주운전 발생건수에 영향을 미치는 주요 변수이다.  

<p align="center">
  <img src="https://github.com/user-attachments/assets/c19d454b-6eae-4012-8dd4-ec53663f9b37" width="600">
</p>

- RandomForest 를 이용하여 도출한 음주운전 발생건수에 영향을 미치는 주요 변수  
: __차량 등록 대수__, __지역구별 인구수__, __횡단보도 개수__, __음식점 수__, __버스 정류장 개수__, __음주운전 사고 건수__

### 음주운전의 다양한 요인들의 영향을 해석 - 상관 분석
1. 요일별 단속건수와 관련 요인 상관 분석
   
<p align="center">
  <img src="https://github.com/user-attachments/assets/10ac6780-50b9-4a20-9804-b32cdc640b18" width="600">
</p>

- 금요일, 토요일, 일요일에 음주운전이 다른 요일에 비해 많아 관련 요인과의 상관 관계를 분석하여 원인을 확인하려고 했으나 요일별로 원인의 영향은 큰 차이를 보이지 않았다.

2. 연령대별 단속건수와 관련 요인

<p align="center">
  <img src="https://github.com/user-attachments/assets/1dacaee1-dfd1-4fea-8bae-9186d552751c" width="600">
</p>

- 10대와 20대는 주점, 지하철역, 택시 정류장이 많은 지역에서 음주운전이 많이 발생한다.
- 30대부터 70대까지는 버스정류장, 가로등, 횡단보도, 신호등이 많은 지역에서 음주운전이 많이 발생하고, 기온이 낮을수록 음주운전이 많이 발생한다.

3. 시간대별 단속건수와 관련 요인

<p align="center">
  <img src="https://github.com/user-attachments/assets/063d72f1-d833-4f1b-a58c-4db71f309559" width="600">
</p>

- 04시~07시까지 주점이 많을수록 음주운전이 많이 발생한다.
- 12시~19시까지 횡단보도 수가 많고 기온이 낮을수록 음주운전이 많이 발생한다.
- 16시~23시까지 버스 정류장과 가로등 수가 많을수록 음주운전이 많이 발생한다.
- 20시~23시까지 신호등 수가 많을수록 음주운전이 많이 발생한다.

### 부산시 군구별 음주운전 성향 파악
1. 요일별 음주운전 건수 군집 분석

<p align="center">
  <img src="https://github.com/user-attachments/assets/038e78e5-9531-4122-b225-18207b39e08c" width="600">
</p>

- **Cluster 0** ['강서구', '금정구', '동래구', '북구', '사상구', '사하구', '연제구']: **중간 수준의 음주운전 건수를 가진 군구**  
주중에는 평균적인 음주운전 건수를 기록  
금요일과 토요일에 높은 건수를 보임. 주말 중심의 음주운전 단속 강화 필요  

- **Cluster 1** ['동구', '서구', '영도구', '중구'] : **음주운전 건수가 가장 낮은 군구.**  
음주운전 문제가 덜 심각한 지역  
모든 요일에서 음주운전 건수가 낮으며, 특히 일요일에 매우 낮은 값을 보임  

- **Cluster 2** ['기장군', '남구', '부산진구', '해운대구'] : **음주운전 건수가 가장 높은 군구.**  
음주운전 문제가 심각한 지역  
모든 요일에서 높은 음주운전 건수를 기록하며, 특히 금요일과 토요일에 가장 높은 값을 보임  
금요일과 토요일에 단속을 강화하고, 심야 시간대 감시를 늘릴 필요  

2. 시간대별 음주운전 건수 군집 분석

<p align="center">
  <img src="https://github.com/user-attachments/assets/187549ec-7ef4-4a10-be4b-3997a5b4eb66" width="600">
</p>

(설명 추가 예정)

3. 연령대별 음주운전 건수 군집 분석

<p align="center">
  <img src="https://github.com/user-attachments/assets/3e8c46cd-ac6c-4912-9847-180b7db318d0" width="600">
</p>

(설명 추가 예정)

</br>

## 3. 예측 모델 구성
<div <div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/user-attachments/assets/d7ff5816-5aa8-4d9b-9f96-485c6f2ee146" width="330">
  <img src="https://github.com/user-attachments/assets/482e98a9-e47d-452f-9d55-635c35fd63e9" width="330">
  <img src="https://github.com/user-attachments/assets/79d42a16-4065-49b4-a1e8-d69a6dbc9163" width="330">
</div>

</br>

## 4. 솔루션 소개 
**KT의 AI & 빅데이터 분석 기술을 활용하여 경찰청과 연계한 단속 전략 최적화 솔루션**  
KT의 기술력으로 실시간 적발 데이터 수집 후 AI 모델 분석하여 즉각적인 조정이 가능케 함  
분석된 데이터를 경찰청으로 자동 전송하여 경찰 측의 대시보드에 연계  
이로 인해 사후 대응 중심의 현 방식에서 사전 차단으로 예방 중심의 단속 방식으로 변경  
AI 기반 데이터 분석 및 실시간 단속 전략 최적화  
데이터 분석 기반 단속 우선 지역을 추천하여 무작위 단속의 저효율을 타파하고, 단속 효율성 증대  


### 대시보드 & 모바일 앱 기능
**공통 기능**
|기능|대시보드|모바일 앱|
|------|---|---|
|로그인|![image (4)](https://github.com/user-attachments/assets/6885d05a-d05a-41bd-b761-ff1dc7f01734)|![image (8)](https://github.com/user-attachments/assets/164244df-3d09-4b6b-9a84-a279eba4e1a6)|
|HOME|![image (5)](https://github.com/user-attachments/assets/0e62594d-45a0-42fc-a3eb-5a3b032917ba)|![image (9)](https://github.com/user-attachments/assets/a41f15d3-a753-4c84-96ab-d46847a6f541)|
|운전자 조회|![image (10)](https://github.com/user-attachments/assets/c41fb12c-cae4-45fd-bbe8-968248a3956a)||
|차량 조회|![image (11)](https://github.com/user-attachments/assets/ad1f4bbb-9bef-49d3-9017-6e025aad7ded)|![image (12)](https://github.com/user-attachments/assets/36dc0511-0d65-4881-9759-6aac20d38799)|
|알림 및 공지|![image (6)](https://github.com/user-attachments/assets/7502bd9e-e89e-471c-8645-d5dbdcf92b39)||
   
**대시보드 기능**
|기능|화면|설명|
|------|---|---|
|통계/정보|![image (13)](https://github.com/user-attachments/assets/cab7ccab-8885-4b43-afe4-839109bc399b)|각 지역별 음주운전 관련 사고 정보 및 기타 정보를 확인 할 수 있습니다|
|차단기 원격 조종|![image (14)](https://github.com/user-attachments/assets/4123f9c8-e886-47c4-a633-a1cad9a4e061)|각 주차장의 차량 차단기를 원격 조종 할 수 있습니다|
|출동 정보 확인|![image (16)](https://github.com/user-attachments/assets/e4541732-a12c-4474-acd7-94ef02ec04d6)|현재 출동한 경찰, 신고 내역, 출동 했던 내용들을 확인할 수 있습니다|
    
**모바일 앱 기능**
|기능|화면|설명|
|------|---|---|
||||
||||
||||

</br>

## 5. 역할 분담
### 🍑 김찬진  
- R&R
    - 조장, PM
- 세부 사항
    - (작성 예정)

### 🍐 오승욱  
- R&R
    - 제안 전략
- 세부 사항
    - (작성 예정) 

### 🍋이수빈  
- R&R
    - 제안 전략
- 세부 사항
    - 데이터 수집 및 데이터 셋 구축
    - 데이터 시각화
    - 모델링

### 🥭 김정훈  
- R&R
    - 사업 제안
- 세부 사항
    - 제안 배경
    - 서비스 흐름도 작성

### 🍓 노준영  
- R&R
    - 기술 PM
- 세부 사항
    - 데이터 수집
    - 데이터 셋 구축
    - 데이터 분석
    - 모델링
    - 인프라 구성

### 🥥 김민영  
- R&R
    - UI/UX
- 세부 사항
    - 데이터 수집 및 데이터 셋 구축
    - 데이터 분석
    - UI 디자인
    - 프로토타입 제작

### 🍊 류민주  
- R&R
    - 데이터 분석
- 세부 사항
    - (작성 예정) 

### 🍉 류선우  
- R&R
    - 제안 전략
- 세부 사항
    - 사업 제안 및 기획
    - 데이터 수집 및 데이터 셋 구축
    - 데이터 분석

</br>

## 6. 프로젝트 기간 및 작업 관리
### 개발 기간  
- 전체 프로젝트 기간 : 2024. 12. 30. ~ 2025. 2. 13.
- UI,UX 구현 :
- 프로토타입 구현 :

### 작업 관리  
- GitHub Projects와 Issues를 사용하여 진행 상황을 공유했습니다.
- 주간회의를 진행하며 작업 순서와 방향성에 대한 고민을 나누고 GitHub Wiki에 회의 내용을 기록했습니다.

</br>

## 7. 프로젝트 후기
(작성후 추가 예정)
