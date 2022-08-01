# PyTorch와 전이학습을 활용한 안저사진 자동판별 기법

### 문제 정의
- 안저 이미지 데이터 수동 판별의 높은 난이도 및 노동집약적 과정
- 양질의 훈련 및 시험용 데이터 부족
- 이미지 도메인 변화에 의한 판별 성능 저하

### 실험 데이터셋
- 다양한 지역(미국, 스페인, 프랑스 등) 소재 의료기관의 연구용 공개 안저사진 데이터셋
- 데이터 증강(augmentation-geometric distortion[rotation], gaussian function 등)
- 의료기관별 30장부터 최대 1296장 구성
- 데이터 소스별 분리, 총 4번의 실험으로 학습 및 시험

### 실험 방법
- 전이학습transfer learning: ImageNet 데이터셋으로 사전훈련된 ResNet-18 모델의 지식의 기반 위 타겟인종과 촬영 장비 등이 상이한 이미지 도메인의 안저사진 fine-tuning, 모델 훈련 및 시험

### 실험 결과
- 총 4회 실험, 최고 97.30%와 평균 96.71%의 정확도 기록, 데이터 부족 문제 해결
- 한계: 기타 의료기관 데이터셋 시험 시 성능 저하 기록, 개선 필요

### 실험 화면

- pre-prossessing:

![preprocessing](https://user-images.githubusercontent.com/71416000/182088913-f148aa04-71a8-4792-af8e-bb393ad92fa2.jpg)


- training model:

![train_model](https://user-images.githubusercontent.com/71416000/182088916-4fbdb1be-f054-4a3f-9eb8-abb90d545bb5.jpg)


- epochs display:

![epochs](https://user-images.githubusercontent.com/71416000/182088911-23713828-1afb-4f18-a6f0-f12d803373e4.jpg)


- validation visualization:

![validatrion_visualization](https://user-images.githubusercontent.com/71416000/182088908-bc6382ae-0b3e-4e35-a73d-c1c88c8652cf.jpg)

- 전이학습 관련 참고:
PyTorch 공식문서 'transfer learning tutorial for computer vision tutorial' at https://github.com/pytorch/tutorials.git by author Sasank Chilamkurthy
