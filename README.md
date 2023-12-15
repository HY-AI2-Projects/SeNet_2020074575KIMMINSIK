
![header](https://capsule-render.vercel.app/api?type=transparent&fontColor=295CC2&text=SeNet&fontSize=60&height=300&desc=Artificial2&descAlignY=70)

# Overview

2020074575 김민식 
인공지능2 수업을 통해 배운 SeNet 구조에 대해서 논문(Squeeze-and-Excitation Networks)을 읽고 해석, 실제 코드를 구현해보았습니다.  


<br />

<img src="https://blog.kakaocdn.net/dn/bIEGhy/btq0BDqfwIE/B1sB7OgCQQ4ZNWXTyZiuuk/img.png" style="width: 505px" />
<img src="https://media.licdn.com/dms/image/D4E12AQHDRmF-dMTNSg/article-cover_image-shrink_720_1280/0/1668201137108?e=2147483647&v=beta&t=bNfXAmkRRGEkp8fFUcg-AwK_7qCqRJ5pHyJApdV1loY" style="width: 505px" />


<br />

# 🤖 모델 설명

- CVPR 발표
- 2017 ILSVRC 우승

SENet은 기본적으로 네트워크 내부에서 중요한 피처에 집중하고 그 중요도를 강화하는 방식으로 작동합니다. 이를 위해 Squeeze-and-Excitation 모듈을 사용합니다.

SENet의 주요 구성 요소는 다음과 같습니다:

1. Squeeze Operation (압축 연산): 입력 피처 맵의 채널별로 평균 풀링을 수행하여 채널마다 하나의 값을 얻습니다. 이를 통해 각 채널의 중요도를 나타내는 요약된 정보를 얻게 됩니다.

2. Excitation Operation (강조 연산): 압축된 정보를 사용하여 각 채널에 대한 가중치를 계산합니다. 이 가중치는 각 채널의 중요성을 반영하게 되며, 이후에 각 채널에 적용됩니다.

3. Scale Operation (스케일 연산): 각 채널에 계산된 가중치를 적용하여 중요한 피처에 대한 강조를 수행합니다. 이를 통해 네트워크는 훈련 중에 더 중요한 피처에 더 많은 주의를 기울일 수 있습니다.

<br />

# 🙋‍♀️ 느낀점

### 김민식
#### SENET을 공부하면서 이미지 분류 모델에 대한 이해도를 좀 더 키울 수 있었습니다. 특히 self-attention에 대한 개념과 이를 비롯한 모델 성능 향상에 기여하는 기술에 대해서 집중적으로 공부할 수 있는 시간이어서 좋았습니다.
