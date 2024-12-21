# 도서 추천 시스템

파이썬 keras를 이용한 도서 추천 시스템 구현
kaggle에서 제공되는 goodbooks 데이터를 활용하였다. 해당 데이터에 존재하는 모든 feature를 활용하지 않고 단순히 사용자가 책을 보고 난 평가 데이터만 활용.
간단한 행렬 dot 연산과 fully conected layer를 이용해서 간단한 추천 모델을 구현

1.Dot 모델을 이용한 추천 시스템 모델 구현
단순히 내적 연산을 이용한 추천 모델 구현
input layer = input을 받기 위한 용도
embedding layer = embedding 용도
flatten layer = 차원을 하나 줄이고 벡터를 피는 용도
dot layer = 행렬곱 연산을 수행하는 용도
layer들을 정의한 후 싸하주고, 만들어진 layer에 function 기반으로 넣어준다.
이렇게 되면 사용자가 책을 본 rating을 예측하는 모델을 만들어서 이를 추천 시스템 모델로 활용하는 것이다. 사용자가 어떤 책을 선호할 지 안할지를 예측할 수 있기 때문.

2.Fully connected layer (Keras Dense layer)를 이용한 추천 시스템 모델 구현
흔히 Deep learning이라고 말하는 형태로 구현.
input layer = input을 받기 위한 용도
embedding layer = embedding 용도
flatten layer = 벡터 차원을 하나 낮춰주어 피는 용도
concatenate layer = 책 벡터와 사용자 벡터를 하나로 합쳐주기 위한 용도
dense layer = dense layer 통과 용도
최종 output은 Dense(1)이다. rating 하나를 예측하기 때문.
그 전에 concatenate 구조 이후 dense layer를 거쳐서 데이터를 표현해준다. 그리고 Dense(1)을 거쳐 rating을 예측해 추천을 해주는 추천 모델 구조.
