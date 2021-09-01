# 치안안전도 예측 경진대회

## 1.사용언어
    -python(pandas, seaborn, matplotlib, scikit-learn, tensorflow), R, jupyter notebook


## 2. 목적 및 개요
    (1)목적
    -17~19년도 치안관련 데이터를 통해 20년도 치안안전도 예측모델을 개발하고 치안안전활동 방향성 제시
    
    (2)데이터
    -112신고, 범죄발생원표, 범죄검거원표, 보안등, cctv, 교통사고, 지구대별인원현황, 화재발생통계, 성연령별인구분포, 1인가구수, 외국인 인구수, 기초수급자현황, 최종학력통계, 공원현황, 유흥업소 및 주점 현황, 비상벨현황 등

    (3)결과
    -MAE(오차값)1.5
    
## 3. 기술 list
      (1) 전처리
        -결측치 처리
        -shapely.geometry와 geopandas를 이용한 위치데이터 처리
        -one-hot encoding
    
      (2) feture engineering
        -R의 All subset regression
    
      (3) Modeling_1
        -Machine learning(regression)
        
      (4) Modeling_2
        -Deep learning(DNN)
        
    
## 4. 세부내용
###  전처리     
        (1) 결측치처리  
        -결측치 삭제 및 결측치 범주형 변수처리
    
<img src="https://user-images.githubusercontent.com/87842980/131620635-da4732b5-6010-46a8-94cc-487a37f153de.png" width="30%"><img src="https://user-images.githubusercontent.com/87842980/131620637-e9bd5e7b-4c7b-47a5-bb77-7e31abdf090a.png" width="30%"><img src="https://user-images.githubusercontent.com/87842980/131620638-2e59446c-4fcb-4898-94e4-a5d6fa41bb55.png" width="30%">

        (2) 위치데이터 처리
        -shapely.geometry와 geopandas를 이용한 위치데이터 처리
![그림5](https://user-images.githubusercontent.com/87842980/131621758-64e04355-e1e0-4e23-b191-decd03fe759b.png)


        (3) one-hot encoding
        -pd.get_dummies  
    
    
    
###  Feature engineering
        R의 All Subset Regression  
        -가장 설명력이 높은 모델을 선택하는 방법  
        -차원의 저주를 해결, 모델링을 위한 변수선택(feature engineering)  
<img src="https://user-images.githubusercontent.com/87842980/131622820-4ada316a-53ae-49c8-8345-f02435612c11.png" width="50%">


###  Modeling
    
#### Ⅰ.Machine learning(regression)
        (1) scaling
        -non-scaling을 포함한 성능향상을 위해 4가지의 데이터 스케일링 작업
        -standard-scaling
        -minmax-scaling
        -robust-scaling
        
        (2) K-fold  교차검증
        -과적합을 방지하여 성능평가 정확도 향상 가능 
        -데이터수가  123개인  현 상황에선 최적의 검증방법
        
        (3) 모델 리스트
![그림11](https://user-images.githubusercontent.com/87842980/131648775-846f104e-c218-4987-b578-24821cfab278.png)

        
        (4) 결과해석
        -변수영향도 분석
 <img src="https://user-images.githubusercontent.com/87842980/131624217-7a9fb509-93b1-46c7-b4a1-381ac44de39f.png" width="50%">
 
 
#### Ⅱ.Deep learning(DNN)
<img src="https://user-images.githubusercontent.com/87842980/131640067-b6b6e124-c854-48b1-b951-acb781f54c6e.png" width="50%">
 

        (1) scaling
        -robust-scaling 및 standard-scaling
        
        (2) 학습횟수에 따른 DNN모델의 MAE점수 변화 그래프
<img src="https://user-images.githubusercontent.com/87842980/131640071-3b8a6a5f-db7e-44a0-bf41-92a9b6d22a6f.png" width="70%">
        



