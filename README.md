
![header](https://capsule-render.vercel.app/api?type=transparent&fontColor=295CC2&text=SeNet&fontSize=60&height=300&desc=Artificial2&descAlignY=70)

# 📁 코드 구현

2020074575 김민식 
- 인공지능2 수업을 통해 배운 SeNet 구조에 대해서 논문(Squeeze-and-Excitation Networks)을 읽고 해석, 직접 코드로 구현해보았습니다.
- 실습해 본 코드는 torchvision 패키지에서 제공하는 STL10 dataset을 사용하였습니다.(10개의 label을 갖으며 train dataset 5000개, test dataset 8000개로 구성됨)
- MobileNetV1 구조에 SEBlock을 적용하였으며 테스트셋 기준 정확도 약 65%, loss: 0.976369의 결과를 확인하였습니다.
- SEBlock을 적용하지 않은 MobileNetV1 모델에 비해 정확도가 2% 정도 높아진걸 확인할 수 있었습니다.

<br />

# 🤖 모델 설명

<img src="https://blog.kakaocdn.net/dn/IPywv/btq0zcVcqFX/mqMgkIwHlujR5KfGk1GIEK/img.png" style="width: 505px" />

- CVPR 발표
- 2017 ILSVRC 우승

SENet은 기본적으로 네트워크 내부에서 중요한 피처에 집중하고 그 중요도를 강화하는 방식으로 작동합니다. 이를 위해 Squeeze-and-Excitation 모듈을 사용합니다.
좀 더 자세히는 당시 NLP에 사용되고 있던 Attention의 개념을 CNN에 적용하여 Channel relationship을 기반으로 전체 피처맵의 시각에서 보다 중요한 피처맵을 찾고 집중하는 방식입니다.
SENet을 통해서 처음으로 convolution layer를 통과한 각 피처맵을 독립적으로 보는게 아닌 하나의 전체적인 문맥으로 보려는 시도를 하게 되었습니다.
SENet의 구조가 강력한 이유는 어떤 CNN이든 가벼운 블록의 형태로 적용하면 놀라운 성능 향상을 일으킬 수 있기 때문입니다.


<img src="https://blog.kakaocdn.net/dn/bIEGhy/btq0BDqfwIE/B1sB7OgCQQ4ZNWXTyZiuuk/img.png" style="width: 505px" />
<img src="https://media.licdn.com/dms/image/D4E12AQHDRmF-dMTNSg/article-cover_image-shrink_720_1280/0/1668201137108?e=2147483647&v=beta&t=bNfXAmkRRGEkp8fFUcg-AwK_7qCqRJ5pHyJApdV1loY" style="width: 505px" />


- SENet의 주요 구성 요소는 다음과 같습니다:

1. Squeeze Operation (압축 연산): 입력 피처 맵의 채널별로  Global 평균 풀링을 수행하여 채널마다 하나의 값을 얻습니다. 이를 통해 각 채널의 중요도를 나타내는 요약된 정보를 얻게 됩니다.

2. Excitation Operation (강조 및 재조정 연산): 압축된 정보를 사용하여 각 채널에 대한 가중치를 계산합니다. 이 가중치는 각 채널의 중요성을 반영하게 되며, 이후에 각 채널에 적용됩니다.

3. Scale Operation (스케일 연산): 각 채널에 계산된 가중치를 적용하여 중요한 피처에 대한 강조를 수행합니다. 이를 통해 네트워크는 훈련 중에 더 중요한 피처에 더 많은 주의를 기울일 수 있습니다.

<br />

# 🛠 다양한 모델에 적용한 SEBLOCK 성능

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc2Ql5x%2Fbtq0BEvXGmG%2FyHkGD6ykgK76djUyR3skLk%2Fimg.png" style="width: 805px" />

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fdcio2U%2Fbtq0EDJ4DF5%2F9KfbdB3dfInlGwFtgMgUkk%2Fimg.png" style="width: 805px" />

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FMmKxN%2Fbtq0z0modCD%2FxtrJiD4uFZg44Vd4Dxnd31%2Fimg.png" style="width: 605px" />


<br />

# 👨‍💻 참조 자료
https://www.youtube.com/watch?v=Ra-x8Mz0m60

<br />

# 🙋‍♀️ 느낀점

### 김민식
#### SENET을 공부하면서 이미지 분류 모델에 대한 이해도를 좀 더 키울 수 있었습니다. 특히 self-attention에 대한 개념과 이를 비롯한 모델 성능 향상에 기여하는 기술에 대해서 집중적으로 공부할 수 있는 시간이어서 좋았습니다. 추가적으로 기존의 이미 사람의 성능을 훨씬 뛰어넘은 분류 기술을 새로운 접근 방식으로 풀어낸 것이 아주 인상적이었습니다.
