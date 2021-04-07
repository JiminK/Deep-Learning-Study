# [ LAB 06 - Softmax Classification ]
---

## Discrete Probability Distribution

: 이산적 확률 분포

- 확률

|| 이산적 | 연속적 |
|--|--|--|
|ex.| 주사위, 가위바위보 |  |

cf) **PDF** (확률밀도함수)

## Softmax

( 0 , 0 , 1 ) 이 아니라 ...
- 합이 1
- 비율로, 확률적으로

## Cross Entropy
**⇒ 최소화하는 것이 중요!**

H(P, Q) = -Ex~p(x)[logQ(x)] = -∑x∈xP(x)logQ(x)

## Cross Entropy Loss (low-level)

>L = ∑-ylog(ˆy) / N

y = P(X), ˆy = Pθ(X)

## Cross Entropy Loss (torch.nn.functional 사용)
**NLL** : 음의 로그 우도(가능도)
⇒ 딥러닝모델의 손실함수

## 참고
cf)    
1. 기존의 Binary Classification    
* Binary Cross Entropy **(BCE)**    
* sigmoid 함수 사용    
  
2. 클래스 여러개    
* Cross Entropy **(CE)**
* Softmax 사용
