 MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications
 =================================================================================
 논문링크: <https://arxiv.org/pdf/1704.04861.pdf>   
 
 Introduction
 ----------------
 > VGG16 Model Archtecture   
  <img src="/paper_review/mobilenetv1/image/1.png" width="80%" height="80%" title="img1" alt="img1"></img>    
 
 기존 CNN Model의 Archtecture을 확인해보면 단순히 채널 수를 증가시키며 convolution-pooling 의 연속으로 구성되어있습니다.
가장 직관적인 구조로 이해도 쉽고 구현하기도 쉽습니다.
하지만 모바일 환경에서 구동시키기엔 convolution 구조가 다소 무겁기 떄문에 파라미터량을 획기적으로 줄이기 위해 MobileNet이라는 Model 구조를 만들었다.


  Depthwise separable convolution
 -------------------------------
 > Convolution Block 비교
 <img src="/paper_review/mobilenetv1/image/2.JPG" width="80%" height="80%" title="img1" alt="img1"></img>    
 > Depthwise separable convolution 
 <img src="/paper_review/mobilenetv1/image/7.JPG" width="80%" height="80%" title="img1" alt="img1"></img>    

Depthwise separable convolution이란 depthwise convolution과 pointwise convolution의 결합으로 보시면 된다.
위의 그림 b에 나오는 Depthwise Convolution은 채널별로 분리하여 각 채널을 각각의 커널로 convolution 하는 것입니다.
이때, 입력의 채널과 출력의 채널은 항상 같습니다.
위의 그림 c에 pointwise convolution은 출력의 채널의 깊이 바꿀 수 있으며, 1x1 conv하는 것을 말합니다.
#### 계산량 비교
> (a)
 <img src="/paper_review/mobilenetv1/image/3.JPG" width="80%" height="80%" title="img1" alt="img1"></img>    

> (b)
 <img src="/paper_review/mobilenetv1/image/4.JPG" width="80%" height="80%" title="img1" alt="img1"></img>    

> (b)+(c)
 <img src="/paper_review/mobilenetv1/image/5.JPG" width="80%" height="80%" title="img1" alt="img1"></img>   
 
>
