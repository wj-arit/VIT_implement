# VIT_implement
### 1) VIT_base -> implement the architecture of vision transformer
### 2) VIT_compare(backbone = vit(ImageNet-21k, finetune = cifar-100)
   - cls토큰을 활용한 이미지 분류와 나머지 토큰들의 GAP로 이미지 분류하는 방식 비교
   - cls와 gap의 결과 비교 & 어텐션 맵 비교

##### 2-1) train&val
<img width="1200" height="693" alt="image" src="https://github.com/user-attachments/assets/e68622fc-c665-4356-8bcd-8f4fbd401f4c" />

#### 2-2) 어텐션 맵 비교
<img width="1431" height="487" alt="image" src="https://github.com/user-attachments/assets/76f281e3-e32e-44bb-8b4f-55aa59222d46" />

<img width="1436" height="485" alt="image" src="https://github.com/user-attachments/assets/e23eadbe-74c3-4713-86d9-9635edfda43c" />

### 3) 결론 및 분석
본 실험에서는 ViT의 분류 방식(CLS Token vs GAP)에 따른 성능 및 어텐션 맵의 변화를 분석하였습니다.

실험 결과: 시각화된 어텐션 맵(Attention Map) 확인 결과, GAP 방식은 CLS 방식에 비해 객체 외의 배경 영역(Background)이 불필요하게 활성화되는 경향을 보였습니다.

성능 분석: 이로 인해 GAP 방식의 정확도가 CLS 방식 대비 약 0.8% 낮게 측정되었으며, 이는 모델이 분류에 핵심적인 특징뿐만 아니라 배경 노이즈까지 학습에 포함했기 때문으로 판단됩니다.

한계점 및 향후 과제: 다만, 실험에 사용된 ImageNet-21k 기반 Pre-trained 모델이 CLS 토큰 활용을 전제로 학습되었기에, GAP 방식의 성능이 저평가되었을 가능성이 있습니다. 향후에는 학습 방식의 편향을 제거하기 위해 각 방식에 최적화된 Fine-tuning 과정을 거쳐 더욱 객관적인 비교 대조를 수행할 예정입니다.




