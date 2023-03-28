## 제주도 도로 교통량 예측 AI 경진대회

대회 URL: https://dacon.io/competitions/official/235985/overview/description

주최/주관 : 제주 테크노파크, 제주특별자치도 / 데이콘

진행 기간 : 2022.10.21 ~ 2022.11.14

대회설명:
  * 제주도내 인구의 증가로 도로의 교통체증(Km/h)을 미리 예측하는 AI 모델 개발(Regression)
  
대회 목표:
  * 도로의 상태, 시간,요일 등을 나타내는 30개 feature 이용하여 특정 도로 평균 시속 예측 AI 모델 개발

대회 결과 :
  * 데이터 전처리, 모델링, 튜닝, 후처리를 이용하여 예측 모델 개발
  * 대회 최종 12등 달성
 * * *
 ## 대회 진행 환경 & 역할
 프로젝트 진행 환경 : Google Colab
 
 팀구성 : 1명
 
 역할 :
  * 데이터 분석
    * 데이터 시각화, feature 제거, 파생변수 생성
  * 모델 개발
    * AutoML을 사용하여 좋은 성능을 내는 모델 선별
    * optuna를 이용하여 각 모델 하이퍼 파라미터 튜닝
    * 앙상블 적용 및 간단한 후처리 진행
* * *
## 진행 상세 과정
1.데이터 분석
  * feature별 데이터 분포 확인
  * 유일값 변수 & 특정 변수 삭제
  
2.파생 변수 생성
  * 날짜, 시간 변수를 이용하여 주기성(sin * cos) feature 생성 외 다수 파생 변수 생성

3.모델링 & 튜닝
  * 50만개 데이터만 랜덤으로 추출 후 AutoML을 이용하여 best model 선택(RF, CatBoost, LGBM)
  * 전체 데이터로 Optuna를 이용한 하이퍼 파라미터 튜닝
  
4.성능 향상 방법
  * Weighted sum 앙상블 진행
    * RF : Catboost : LGBM = 5 : 3 : 2
  * 결과값 후처리 ( 반올림 - Train에서의 모든 y값은 소수값을 가지지 않음 )
