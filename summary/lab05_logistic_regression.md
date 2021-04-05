# [ LAB 05 - Logistic Regression ]
---

"논리적 회귀"    

**Logistic Regression**    
⇒ 바이너릭 문제

* Hypothesis (가설) :    
>H(x) = 1 / 1 + e^(-W ^T^ X)    
⇒ **1 / 1 + e^(-XW)**    

H(x) ≒ P(X=1)    
| XㆍW | = ( m , d ) x ( d , 1 ) = ( m , 1 ) **⇒ m개의 element를 가진 1차원...**

cf) P(X=1) = 1 - P(X=0)

* Cost :
> Cost(W) = -∑(ylog(H(x)) + (1 - y)(log(1 - H(x)))) / m

* (참고)
H(x) = P(x=1 ; w) = 1 - P(x=0 ; w)    
⇒ **H(x)는 w가 주어졌을 때 x=1의 확률**


## Gradient Descent

W := W - α∂Cost(W) / ∂W    
= W - α∇wCost(W)    
(α : learning rate)    


## Computing the Hypothsis

* **hypothesis** = 1 / (1 + torch.exp(-(x_train.matmul(W) + b)))    
= torch.sigmoid(x_train.matmul(W) + b)    
> x_train.matmul(W) = XㆍW = torch.matmul(X, W)

이때, W = torch.zeros((2, 1), requires_grad=True)    
b = torch.zeros(1, requires_grad=True)    
> **requires_grad=True** : 그 tensor에서 이뤄진 모든 연산 추적(track) / gradient를 배우도록 설정

* **loss** = -(y - train[0] * torch.log(hypothesis[0]) + (1 - y_train[0]) * torch.log(1- hypothesis[0]))    
> torch.log(hypothesis[0]) ... **scala = logP(X=1 ; W)**    
> torch.log(1- hypothesis[0]) **= logP(X=0 ; W) = 1 - logP(X=1 ; W)**

* **cost** = losses.mean()
    
⇒ F.binary_cross_entropy(hypothesis, y_train)

## Evaluation (정확도 체크)
* **hypothesis** = torch.sigmoid(x_test.matmul(W) + b)

* **prediction** = hypothesis ≥ torch.FloatTensor([0.5])
> *prediction의 type : **Byte Tensor***

* prediction, y_train 비교    
⇒ correct_prediction = **prediction.float() == y_train**

cf) **Stochastic Gradient Descent (SGD)** : 확률적 경사 하강법    
"추출된 **데이터 한 개**에 대해서 error gradient 계산하고 Gradient Descent 알고리즘 적용"

