# [LAB 01] " Tensor Manipulation " 
---

 
 - 2차원 matrix(행렬)    
 
**| t | = ( batch size , dim )**    
|t| : tensor size,      
dim : dimension     
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/0_1.png"  width="345" height="250">    


 - 3차원 tensor    
 
**| t | = ( batch size , width , height )**      
**= ( batch size , length , dim )**     
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/0_2.png"  width="402" height="350">     
  
 
## Pytorch의 Broadcasting  
 
> **Note:** 자동으로 적용되므로 주의!     
 
- matrix 간 덧셈, 뺄셈, 연산할 때는 두 tensor의 크기가 같아야 함.     
- 곱셈할 때는 마지막 차원 - 첫번째 차원 같아야 함     
 
다른 크기의 행렬을 연산해야하는 경우     
→ pytorch의 broadcasting 기능 사용     
→ 자동으로 사이즈 맞춰서 연산 가능하게 함.     
 

 

## Matrix Multiplication (행렬곱)

일반 곱 != 행렬곱

 **1. 일반 곱**    

- 행렬 예시    
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/1_1.png"  width="429" height="120">    

- 계산    
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/1_2.png"  width="364" height="250">    
 
 **2. 행렬곱**    

- 행렬 예시    
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/1_3.png"  width="458" height="200">     

- 계산    
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/1_4.png"  width="350" height="250">     


## Mean

ex.
>1 2     
3 4
 1. t.mean()
 **전체 평균** :  2.5
 
 2. t.mean(dim=0)    
 **첫번째 dimension의 평균  ⇒  열 기준** :    
i) 1, 3의 평균 : 2    
ii) 2, 4의 평균 : 3    

3. t.mean(dim=1)    
**두번째 dimension의 평균 ⇒ 행 기준**    
i) 1, 2의 평균 : 1.5    
ii) 3, 4의 평균 : 3.5    

4. t.mean(dim=-1)    
**첫번째 dimension의 평균  ⇒  열 기준** (*2와 동일*) :    
i) 1, 3의 평균 : 2    
ii) 2, 4의 평균 : 3    


## Sum
mean 과 동일


## Max / Argmax
Max : 가장 큰 값
Argmax : 가장 큰 값의 인덱스 값


## View
≒ numpy의 reshape 함수    

ex.
> t = [ [ [ 0 , 1 , 2 ] , [ 3 , 4 , 5 ] ] , [ [ 6 , 7 , 8 ] , [ 9 , 10 , 11 ] ] ]
    
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/2_1.png"  width="387" height="300">      
     
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/2_2.png"  width="418" height="250">      


| ft | = ( 2 , 2 , 3 )

* ft.view([-1, 3])     
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/2_3.png"  width="291" height="300">      

* ft.view([-1, 3]).shape   
⇒ ( 4 , 3 )    
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/2_4.png"  width="447" height="250">      

* ft.view([-1, 1, 3])    
<img src="https://github.com/JiminK/Deep-Learning-Study/blob/main/img/2_5.png"  width="605" height="320">      

## Squeeze
view와 비슷함.     

자동으로 내가 원하는 dimension     
or 전체에서 하나밖에 없는 dimension 삭제



## Unsqueeze
내가 원하는 dimension에 1 넣어줌.

>**Note:** 꼭 dimension 명시!



## Type Casting

 - .float()
 - .long()
 - .ByteTensor
 


## Concatenate
이어 붙이는 것



## Stacking
concatenate 단순하게



## Ones / Zeros

 - .ones_like(x)
 - .zeros_like(x)
 
 
 **똑같은 shape**를 가진 tensor 선언
 
**같은 device의 tensor를 선언**


## In-place Operation


