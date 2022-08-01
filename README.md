# PyTorch와 전이학습을 활용한 안저사진 자동판별 기법

### 문제 정의
- 안저 이미지 데이터 수동 판별의 높은 난이도 및 노동집약적 과정
- 양질의 학습 및 검증용 데이터 부족
- 이미지 도메인 변화에 의한 판별 성능 저하

### 실험 데이터셋
- 다양한 지역(미국, 스페인, 프랑스 등) 소재 의료기관의 연구용 공개 안저사진 데이터셋
- 데이터 증강(augmentation-geometric distortion[rotation], gaussian function 등 활용)
- 기관별로 최소 30장에서부터 최대 1296장까지 구성
- 총 4번의 실험으로 나누어 훈련 및 검증

### 실험 방법
- 전이학습transfer learning기법 적용: 120만장의 ImageNet 데이터 셋으로 사전 훈련된 ResNet-18의 지식을 기반 위에, 타겟인종과 촬영 장비 등이 다양한 이미지 도메인의 안저사진을 fine-tuning하여 모델 훈련 및 검증

#### 실험 결과
- 총 4번의 실험 중 최고 97.30%와 평균 96.71%의 정확도 기록

- pre-prossessing:
![preprocessing](https://user-images.githubusercontent.com/71416000/182088913-f148aa04-71a8-4792-af8e-bb393ad92fa2.jpg)

- training model:
![train_model](https://user-images.githubusercontent.com/71416000/182088916-4fbdb1be-f054-4a3f-9eb8-abb90d545bb5.jpg)

- epochs display:
![epochs](https://user-images.githubusercontent.com/71416000/182088911-23713828-1afb-4f18-a6f0-f12d803373e4.jpg)

- validation visualization:
![validatrion_visualization](https://user-images.githubusercontent.com/71416000/182088908-bc6382ae-0b3e-4e35-a73d-c1c88c8652cf.jpg)

- 전이학습 관련 참고 코드소스:
PyTorch 공식문서 'transfer learning tutorial for computer vision tutorial'
https://github.com/pytorch/tutorials.git
Author: Sasank Chilamkurthy
