# [ LAB 09 (1) - ReLU ]
---

## Sigmoid 함수 문제점

" Input → Network → Output "    
**정답 - output ⇒ Loss 계산**    
(ex. CE 사용)    

- **Loss ⇒ Gradient 구함** (by 미분)    
Backpropagation 알고리즘 사용,    
weight 업데이트 학습    

⇒ 이때, sigmoid 문제 발생!!

<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/5_1.png"  width="408" height="300">    

**" Vanishing Gradient "**    
: Gradient 소멸    

⇒ **ReLU**를 통해 해결!    


## ReLU

>**f(x) = max(0, x)**    

입력으로 들어온 x가    
- 0보다 크다 ⇒ x    
- 0보다 작다 ⇒ 0    
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/5_2.png"  width="569" height="250">    

x = torch.nn.sigmoid(x)    
⇒ **x = torch.nn.relu(x)**    

cf) torch.nn.reaky_relu(x, 0.01)    


## 디양한 Optimizer들 ...

