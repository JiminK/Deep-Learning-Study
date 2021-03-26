# [ LAB 04 (1) - Multivariable Linear Regression ]
---

"여러 개의 정보로부터 하나의 추측값 계산"

* **Multivariate Linear Regression**
* .matmul() 사용
* nn.Module 상속
* .mse_loss() : pytorch의 cost function     
     
---
# [ LAB 04 (2) - Loading Data ]
---

"많은 데이터를 편하게 관리하는 법"


* **Simple** linear regression
*  **Multivariate** linear regression

데이터 多 ...
| 장점 | 단점 |
|--|--|
| **견고**하다 | 각 데이터들의 cost를 구해야 하므로 **연산 속도가 느려진다**
**완성도**가 높다 | 저장을 못 할 수도 있다 |

따라서,  한 번에 학습시키는 것 불가능    
⇒ **일부분만 학습**시키자!    
⇒ **" Mini batch Gradient Descent "**

## Mini batch Gradient Descent
전체 데이터를 적은 양 (mini batch) 으로 균일하게 나눠서    
mini batch 하나하나를 학습시키는 방법.

- 한 번의 업데이트 마다 **계산할 cost의 양 ↓**    
⇒ **업데이트 주기 ↓** (빨라짐)

- 하지만, **정확도 ↓**    
⇒ 매끄럽 X, 거칠게 O


## Pytorch Dataset
- pytorch에서 제공하는 모듈
- 이를 상속해 원하는 데이터셋 지정 가능

두 method 구현해야함

 1. **__ len__()** : 데이터셋의 총 데이터 수 반환
 2. **__ getitem__()** : 어떤 인덱스를 받았을 때, 그에 상응하는 입출력 데이터를 torch.Tensor 형태로 바꿔서 반환


## Pytorch DataLoader
- 데이터셋, 각 minibatch의 크기 지정해줘야 함.

- **minibatch의 크기**는 **2의 제곱수**로.    
(ex. 16, 32, 64, 128, 256 ...)

- 많이 사용하는 옵션

     - **shuffle=True**    
: **데이터의 학습 순서를 바꿈**    
⇒ 모델이 **데이터셋 순서 외우는 것 방지**     
웬만하면 사용하기!!

     - **enumerate(dataloader)**     
: **minibatch의 인덱스, 데이터** 받음     
이를 통해 x, y 설정 가능 ⇒ **gradient descent** 수행 가능     
