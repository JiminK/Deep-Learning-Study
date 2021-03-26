# [ LAB 02 - Linear Regression ]
---
pytorch로 linear regression 구현
⇒ 주어진 데이터로 최선의 예측을 하도록 학습시키기.

| training data set | test data set |
|--|--|
|  | 학습이 잘 끝난 후 모델이 잘 작동하는지 판별하기 위한 데이터셋 |

* Hypothesis
> y = Wx + b

처음엔 weight, bias 를 0으로 초기화
**W, b를 학습시키는 것이 우리의 목적**

## loss 계산하기
**Mean Squared Error (MSE)**
=  (예측값 - 실제 training data의 y값의 차이)^2 의 평균
