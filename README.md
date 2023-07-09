# Portfolio
Seokwon Na's portfolio projects collection

### 1. KaggleProject - Chest X Ray pneumonia
- https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

#### Pre-trained model을 활용한 architecture 사용
#### Model architecture 1 
- pretrained model : MobileNet(weights=imagenet) - F - D - D
- dropout: 0.5
- number of node : 16
- optimizer : Adam
- learning rate : 2e-5
- epochs : 40
- Test
    loss: 1.6094, accuracy: 0.7933
- Elapsed Time :  0:26:04.697911
  
  ![20230706 project -1 MobileNet](https://github.com/naleetwo/Portfolio/assets/109716149/943e44bf-b73a-4939-8e6a-992a6db84e87)

#### Model architecutre 2
- pretrained model : MobileNet(weights=imagenet) - F - D - D
- dropout: 0.5
- number of node : 16
- optimizer : Adam
- learning rate : 1e-7
- epochs : 80
- Test
    loss: 0.0528 - accuracy: 0.9923

  ![20230706 project -2 loss accuracy](https://github.com/naleetwo/Portfolio/assets/109716149/f7341edd-bd9e-49e8-bb2a-2b4190e23dbe)

Model A1과 같은 architecutre를 사용하였으나 learning rate 를 더 낮추고 epochs를 더 늘림으로서 정확도와 오차를 줄였다. 하지만 훈련 시간은 더 길어지는 결과를 가지게 됨.

#### Model architecture 3
- pretrained model : ResNet50(weights=imagenet) - F - D - D
- dropout: 0.5
- number of node : 16

---------------------------------------------------------------------------------
    Total params: 23,620,530
    Trainable params: 23,567,410
    Non-trainable params: 53,120
---------------------------------------------------------------------------------

- optimizer : Adam
- learning rate : 1e-5
- epochs : 50
- Test
    loss: 0.1454 - accuracy: 0.9744
- Validation 
    loss: 0.1774 - accuracy: 0.9679
- Elapsed Time :  0:28:48.598998


  ![20230707 project 3_ResNet50](https://github.com/naleetwo/Portfolio/assets/109716149/fb9b64a0-87b6-4186-98a7-9eef41fe3947)

ResNet50 모델을 사용 하였으며  mobilenet model a1 보다 epoch 수가 더 많게 함으로서 정확도나 loss 값이 더 나아졌으나 현재 Test 해본결과 같은 data를 가지고 pre-trained 모델의 종류 비교 및 효율성 비교를 해야 할 시 optimizer와 learning rate 그리고 epoch 의 환경을 같게하여 비교해야 할 필요성을 느낌
 - 동일한 tuning 조건에서 학습시키지 않을시 성능비교를 할 수 없음
 - 모델학습 참고 링크 : https://yeong-jin-data-blog.tistory.com/entry/%EC%82%AC%EC%A0%84%ED%95%99%EC%8A%B5-%EB%AA%A8%EB%8D%B8-CNN

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Model 을 사용해보았지만 아직 딥러닝의 확실한 이해도가 낮기 때문에 딥러닝 모델에 대한 이해도를 높이기위해 관련 논문 및 설명을 참고해서 각 모델링의 특징과 차이점을 좀 더 비교분석해봐야 할것같음
- MobileNet 참고링크 : https://velog.io/@woojinn8/LightWeight-Deep-Learning-6.-MobileNet-2-MobileNet%EC%9D%98-%EA%B5%AC%EC%A1%B0-%EB%B0%8F-%EC%84%B1%EB%8A%A5
- ResNet 설명 및 정리 : https://ganghee-lee.tistory.com/41

