Binary Classification
=====================
실험주제
-------
다양한 classification Model을 이진분류 개 고양이 분류 데이터를 활용하여 동일한 하이퍼 파라미터 상에서
성능을 비교하고 상위 2개 모델의 Attention SE Block을 추가하여 성능 향상의 여부를 판별.

실험환경
--------
* Google Colab Gpu 을 사용하였음.
* Colab 내장 라이브러리 PyTorch '1.5.0+cu101' 환경

DataSet
-------
> Image Example   
   
<img src="/workspace/binary_classification/image/1.JPG" width="80%" height="80%" title="img1" alt="img1"></img>   

> 분류 그래프   
   
<img src="/workspace/binary_classification/image/2.JPG" width="80%" height="80%" title="img2" alt="img2"></img>   

* 데이터셋은 다음의 링크를 참조 : <https://www.kaggle.com/c/dogs-vs-cats/data>   
* 데이터 포맷 형식 : jpg   
* 데이터 분류 방식 : Download 한 Daataset 내부 Train dataset 25000장 을 배열 슬라이스를 통하여 Train iamge 17000장, vaildation image 4000장, test image 4000장으로 나누어서 실험하였다.(분류 그래프 참조)
* 이미지 해상도 :
* class : 개, 고양이

Augmentation
------------
* Train Dataset :Resize, RandomHorizontalFlip
* Validation, Test Dataset : Resize

Hyperparameter
--------------
* epoch : 200 
* image size : height = 224, width = 224, channel = 3 로 변환
* optimizer : SGD ( decay = 5e-4, momentum = 0.9 )
* learning rate : 1e-5

Training
----------
```
python main.py -h

```
실험결과
-------

***
### Training & Validation Graph 비교
### Test Dataset의 Accuracy 비교
