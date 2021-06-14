[![hackmd-github-sync-badge](https://hackmd.io/YMF0dDwUSw6ObPV0FgZyxA/badge)](https://hackmd.io/YMF0dDwUSw6ObPV0FgZyxA)
MIMO final project-massive MIMO.md
---
# MIMO final project-massive MIMO

## 1.	Introduction
Due to using millimeter wave to transfer signals in 5G, it means that the antenna has a more limited range. To conquer this disadvantage, we need to increase the number of antennas. That’s the main reason we use massive MIMO in 5G. Although massive MIMO can reach the conquer the limited range, but it still brings many new challenges, such as: channel estimation, precoding and signal detection. In this proposal, we are going to discuss about the signal detection in massive MIMO system.

## 2.	Problem Description
Although the ML detection can be used in massive MIMO system, but the complexity increases exponentially when the number of antenna increase. There are many detection solutions based on linear and non-linear methods. In this proposal, we focus on linear detectors with approximate matrix inversion. Besides, there is a challenge in linear detectors based on the approximate matrix inversion. If the matrix is nearly singular, the system may be ill-conditioned. There are many methods to reduce the complexity of the matrix inversion have been proposed. We discuss many algorithm of linear detectors based on the approximate matrix inversion, to compare the pros and cons of different method.

## 3.	Method and Plans
We study different methods. According to each method’s simulation, we survey and compare the pros and cons of different method. We discuss the linear detectors based on the approximate matrix as followings :
-    A.	Maximum likelihood (ML)
-    B.	Minimum Mean Square Estimation (MMSE)
-    C.	Neumann Series Method (NS)
-    D.	Succesive Over-Relaxation (SOR)
-    E.	Gauss-Seidel Method (GS)
-    F.	Jacobi Method
-    G.	Conjugate Gradients Method(CG)
-    H.	Optimized Coordinate Descent Method (CD)
-    I.	Richardson Method
-    
## 4.	Expected Outcome
According to the survey of the linear detectors based on the approximate matrix ,we wish to find out a more feasible method for the massive MIMO detections. It provides low complexity, low computational complexity, high performance or else.

## 5.	References
[1]	B. Kang, J. Yoon and J. Park, "Low complexity massive MIMO detection architecture based on Neumann method," 2015 International SoC Design Conference (ISOCC), Gyeongju, Korea (South), 2015, pp. 293-294
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7401703
> 
[2]	X. Gao, L. Dai, Y. Hu, Z. Wang and Z. Wang, "Matrix inversion-less signal detection using SOR method for uplink large-scale MIMO systems," 2014 IEEE Global Communications Conference, Austin, TX, USA, 2014, pp. 3291-3295
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7037314

[3]	L. Dai, X. Gao, X. Su, S. Han, C. I and Z. Wang, "Low-Complexity Soft-Output Signal Detection Based on Gauss–Seidel Method for Uplink Multiuser Large-Scale MIMO Systems," in IEEE Transactions on Vehicular Technology, vol. 64, no. 10, pp. 4839-4845, Oct. 2015
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6954512

[4]	F. Jiang, C. Li and Z. Gong, "A low complexity soft-output data detection scheme based on Jacobi method for massive MIMO uplink transmission," 2017 IEEE International Conference on Communications (ICC), Paris, France, 2017, pp. 1-5
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7996693

[5]	B. Yin, M. Wu, J. R. Cavallaro and C. Studer, "Conjugate gradient-based soft-output detection and precoding in massive MIMO systems," 2014 IEEE Global Communications Conference, Austin, TX, USA, 2014, pp. 3696-3701
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7037382

[6]	M. Wu, C. Dick, J. R. Cavallaro and C. Studer, "High-Throughput Data Detection for Massive MU-MIMO-OFDM Using Coordinate Descent," in IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 63, no. 12, pp. 2357-2367, Dec. 2016
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7755889
**先不做**

[7]	X. Gao, L. Dai, C. Yuen and Y. Zhang, "Low-Complexity MMSE Signal Detection Based on Richardson Method for Large-Scale MIMO Systems," 2014 IEEE 80th Vehicular Technology Conference (VTC2014-Fall), Vancouver, BC, Canada, 2014, pp. 1-5
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6966041

[8]	M. A. M. Albreem, A. A. El-Saleh and M. Juntti, "On Approximate Matrix Inversion Methods for Massive MIMO Detectors," 2019 IEEE Wireless Communications and Networking Conference (WCNC), Marrakesh, Morocco, 2019, pp. 1-6
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9037579


# 整理-不同method數學推導

## Neumann Method 

1.  Coventional Neumann Method 


    
    
\begin{gather*}
Y = H \cdot S +n \\
H^H(HH^H)^{-1}\cdot Y = H^H(HH^H)^{-1}\cdot S +n\\
A_K^{-1} = \sum_{n=1}^{K}(D^{-1}E)^{n-1} \cdot D^{-1}\\
A_1^{-1} = D^{-1}\\
A_2^{-1} = D^{-1} - D^{-1}ED^{-1}\\
A_3^{-1} = D^{-1}-D^{-1}ED^{-1}+D^{-1}ED^{-1}ED^{-1}
\end{gather*}




    
* approximated  pseudo-inverse  matrix $A_k^{-1}$
* $D$  denotes  diagonal  matrix  of  GRAM  matrix  $(H^HH)$
* $E$  means off-diagonal elements of GRAM matrix


    ![](https://i.imgur.com/d0vjAe8.png)


2. Proposed Neumann Method 


\begin{gather*}
A_d^{-1} = D^{-1} - D^{-1}ED^{-1} + X_d
\end{gather*}
    
\begin{gather*}
X_d = diag(X) + \sum_{1}^{T}diag_T(X) (T >= |i-j|)
\end{gather*}
    
*  $X_d$ denotes  the approximated $X$ matrix
    
* offset $T$ between the row index (i) of $X_{ij}$ and the column index (j)of $X_{ij}$ is set to 1, 2 and 3

Since the proposed  approach  uses  only  numerically  dominant  (diagonal  and near diagonal) elements of channel  matrix  for  a  low  com-plexity  matrix  inversion,  the  computational  complexity  of  ap-proximated  pseudo-inverse  matrix  is  reduced  to $O(N_U^2)$


## Successive overrelaxation (SOR) Method

### $N$  antennas at the BS to simultaneously serve  $K$ single-antenna UE N>>K


$s_c =\left[ s_{c,1},... s_{c,K}\right]^T$ transmitted signal
$\qquad H_c\in \mathbb{C}^{N*K}$

$y_c = H_cs_c+n_c \qquad     n_c$ distribution $CN(0,\sigma^2)$

$H = 
\begin{bmatrix}
Re(H_c) & -Im(H_c) \\
Im(H_c) & Re(H_c) 
\end{bmatrix}_{2N\times2K}$


$\hat{s}=(H^HH+\sigma^2I_{2K})^{-1}H^Hy=W^{-1}\hat{y}$ $\qquad\hat{y}=H^Hy$


MMSE filtering matrix $W = G+\sigma^2I_{2K}$

Gram matrix $G = H^HH = H^TH = G^T$

### Matrix inversion-less signal detection utilizing SOR method

**Lemma  1.** For uplink large-scale MIMO systems, the MMSE filtering matrix $W$ is symmetric positive definite.

$(Hr)^THr=r^TGr>0$

The SOR method is used to solve N-dimension linear equation Ax=b, where A is the N×N **symmetric positive definite matrix**, x is the N×1 solution vector, and b is the N×1 measurement vector.

diagonal component $D_A$
,lower triangular component $L_A$

$x^{(i+1)}=(L_A+\frac{1}{\omega}D_A)^{-1}\left[ (( \frac{1}{\omega}-1)D_A-L_A^T )x^{(i)}+b\right]$

$W=D+L+L^T$

$s^{(i+1)}=(L+\frac{1}{\omega}D)^{-1}\left[ (( \frac{1}{\omega}-1)D-L^T )s^{(i)}+\hat{y}\right]$

**SOR method:**
$(L+\frac{1}{\omega}D)s^{(i+1)}=\hat{y}+ (( \frac{1}{\omega}-1)D-L^T )s^{(i)}$


**Lemma 2.** For uplink large-scale MIMO systems, the signal detection algorithm using the SOR method is convergent when the relaxation parameter $\omega$ satisfies 0<$\omega$<2.


Since the **complexity** of theclassical MMSE algorithm is $O(K^3)$

Conventional Neumann series approximation algorithm can reduce the complexity from $O(K^3)$ to $O(K^2)$ when the number of iterations is i=2, but the complexity isstill $O(K^3)$ when i≥3.

The SOR-based algorithm can iteratively realize the MMSE solution without complicated matrix inversion, which can reduce the complexity from $O(K^3)$ to $O(K^2)$.

## Gauss–Seidel　（ＧＳ） Method

we propose to use the diagonal component of the  MMSE  filtering  matrix  to  obtain  a  diagonal-approximate  initial solution  to  the  GS  method,  which  can  accelerate  the  convergence rate. After that, we propose an approximated method to calculate the channel  gain and the **noise-plus-interference  (NPI) variance for log-likelihood ratio (LLR)** computation, which also utilizes the diagonal dominant property of the MMSE filtering matrix.


### Ａ．$N$  antennas at the BS to simultaneously serve  $K$ single-antenna UE N>>K

$\hat{s}=(H^HH+\sigma^2I_{K})^{-1}H^Hy=W^{-1}\hat{y}$ 

MMSE filtering matrix $W = G+\sigma^2I_{K}$

### Ｂ．Signal Detection Algorithm Based on GS Method

$W=D+L+L^H$

$s^{(i)}=(D+L)^{-1}\left[  \bar{y}-L^Hs^{(i-1)}\right]$

$i$ is the number of iterations, and $s^{(0)}$ denotes the initial solution

### Ｃ．Diagonal-Approximate Initial Solution

$\frac{h_m^Hh_k}{N}\to 0\qquad m\not=k\qquad m,k=1,2,...,K$

$h_m$ denotes themth column vector of the channel matrix $H$

$s^{(0)}=D^{-1}\hat{y}$

increasing  value  of $N/K$, the  difference  between  the  diagonalmatrix $D^{−1}$ and the nondiagonal matrix $W^{−1}$ becomes smaller.

### Ｄ．Approximated Method to Compute LLRs

略

### Ｅ．Computational Complexity Analysis

To sum up, the overall required number of complex multiplicationsby the proposed GS-based algorithm is $(i+1)K^2+4K$

complexity is $O(K^2)$


## Jacobi Method

### Linear MMSE Detection
$U=K$

$\hat{x}=(H^HH+\sigma_z^2I_{K})^{-1}H^Hy=W^{-1}\hat{y}$

$\hat{y} = y^{MF} = H^Hy$

$W = G+\sigma_z^2I_{K}$


### Jacobi Iterative Method

$W\hat{x} = \hat{y}$

$x^{(k+1)}=D^{-1}\left[ (D-W) \hat{x}^{(k)}+\hat{y}\right]$

$D = diag(W)$

convergence condition for Jacobi iterative method:

$\lim\limits_{k\to \infty}(I_u-D^{-1}W)^k=0$

$x^{(0)}=D^{-1}\hat{y}$

using Jacobi iterative method

$x^{(k+1)}=(\sum\limits_{l = 0}^{k+1}{-D^{-1}(W-D)}^lD^{-1})\hat{y}$

That is to say, the Jacobi iterative method is equivalent to the Neumann series expansion, but using the iterative method to approach the MMSE estimation.

### Computational Complexity
With the proposed matrix vector product, we avoid the matrix multiplications and the overall computational complexity is reduced to $O(B×U)$


## Conjugate Gradients Method

### CG-Based data detection and precoding - Conjugate Gradient (CG) Basics

$\hat{g}=\begin{equation}
	\mathop{\arg\min}_{\tilde{g}\in  \mathbb{C}^U} \ \ \| \mathrm{b-A\tilde{g}} \|.
\end{equation} \qquad A\in \mathbb{C}^{U\times U}$

In  contraryto  direct  methods  that  compute $\hat{g}=A^{−1}b$,  CG  iterativelycomputes  the  solutionˆgwith  each  iteration  requiring  lowcomputational complexity.

### CG-D: CG-Based Soft-Output Data Detection

$\hat{x}=\begin{equation}
	\mathop{\arg\min}_{\tilde{x}\in  \mathbb{C}^U} \ \ \| \mathrm{H_u^Hy-A\tilde{x}} \|.
\end{equation}$

$A= H_u^HH_u+\rho_u^{-1}I_U$

```
1:input:
2:Huandy{detection}
3:Hdandt{precoding}
4:initialization:
5:b=HHuyandA=HHuHu+%−1uIU{detection}
6:b=tandA=HdHHd+%−1dIU{precoding}
7:v0=0,r0=b, andp0=r0
8:for k= 1,...,K do
9:ek−1=Apk−1
10:αk=‖rk−1‖2/(pHk−1ek−1)
11:vk=vk−1+αkpk−1
12:rk=rk−1−αkek−1
13:βk=‖rk‖2/‖rk−1‖2
14:pk=rk+βkpk−1
15:computeμi|k,∀i, as in (14){detection}
16:computeρi|k,∀i, as in (15){detection}
17:end for
18:output:
19:ˆxK=vK,μi|K,∀i, andρi|K,∀i,{detection}
20:qK=HHdvK{precoding}
```

### SINR Computation Methods

$\hat{x_k}=L_kH_u^Hy$

$L_kH_u^H$ CG-equivalent equalization matrix

......

Another well-known variant of CG is the so-called conjugate gradient  least  squares  (CGLS)  method

$\hat{x}=\begin{equation}
	\mathop{\arg\min}_{\tilde{x}\in  \mathbb{C}^U} \ \ \| \mathrm{\bar{y}-\bar{H_u}\tilde{x}} \|.
\end{equation}$


### Computational Complexity Analysis

![](https://i.imgur.com/wff1DIF.png)


## Richardson Method

$\hat{s}=(H^HH+\sigma^2I_{2K})^{-1}H^Hy=W^{-1}\hat{y}$

MMSE filtering matrix $W = G+\sigma^2I_{2K}$

### Signal detection based on Richardson method

**Lemma  1.** For signal detection in uplink large-scale MIMO　systems, the MMSE filtering matrix $W$ is symmetric positive definite

The Richardson method is used to solve N-dimension linear equation formulated as
$Ax=b$

$x$ is the N×1 solution vector, and $b$ is the N×1 measurement vector

$x^{(i+1)}=x^{(i)}+\omega(b-Ax^{(i)}) \qquad i=0,1,2...$

$s^{(i+1)}=s^{(i)}+\omega(\hat{y}-Ws^{(i)}) \qquad i=0,1,2...$

**Lemma  2.** For the N-dimension linear equation $Ax=b$, the necessary and sufficient conditions for convergence of Richardson method is that the relaxation parameter satisfies $0<w<2/λ1$ ,  where $λ1$ is the largest eigenvalue of the symmetric positive definite matrix $A$. 

iteration matrix $D = I_N-\omega A \qquad c=\omega b$

$\rho (D)=\begin{equation}
	\mathop{\max}_{1\le n\le N} \ \| \mathrm{\mu_n (D)} \|.
\end{equation}<1$

$\mu_n (D)=1-\omega \lambda_n \qquad \lambda_n$denotes the $n$th eigenvalue of $A$

### Zone-based initial solution
The last task in the Richardson method is to determine the initial solution, which is usually set as a zero vector

**Lemma  3.** For uplink large-scale MIMO systems, we always have $\hat{s_i} \hat{y_i}$ , where $\hat{s_i}$ and $\hat{y_i}$ denote the $i$th element of $\hat{s}$ and $\hat{y}$, respectively.

$\hat{s_i} \hat{y_i}=(\sum\limits_{j = 1}^{2K}{W_{ij}^{-1}\hat{y_i}})\hat{y_i}\approx W_{ii}^{-1}\hat{y_i}\hat{y_i}>0$

![](https://i.imgur.com/WEqy0Ip.png)


### Computational complexity analysis

the complexity of the proposed algorithm is considerably reduced from $O(K^3)$ to $O(K^2)$ for any arbitrary number of iterations.


## Approximate Matrix Inversion Methods vs. Approximate Message Passing (AMP) 

$y  =  Hx  +  n$

Linear detector stands on a linear transformation of the output signal vectory using a linear equalization/transformationmatrix T which is given as

$d = Ty$

### pproximate matrix inversion methods

1. SOR method

    $\hat{x}^{(n)}=(\frac{1}{\omega}D+L)^{-1}(\hat{x}_{MF}+((\frac{1}{\omega}-1)D-U)\hat{x}^{(n-1)})$
    
    SOR  method  isconvergent when $ω$ satisfies $0<ω<2$
    
2. GS method
    
    $\hat{x}^{(n)}=(D+L)^{-1}(\hat{x}_{MF}-U\hat{x}^{(n-1)}) \qquad n=1,2,...$
     
     the GS method is not suitable for parallelimplementation
    

### pproximate message passing
Simplifying the belief  propagation(BP) algorithm produces  a  new  class  of  low-complexity  iterative  algorithms named as approximate message passing (AMP)

$z^n=y-Hx^{n-1}+\frac{K}{N}\frac{\sigma^2}{\sigma^2+ \alpha^{n-1}}z^{n-1}$

$\alpha^n=N_o^2+\frac{K}{N}\frac{\alpha^{n-1}\sigma^2}{\sigma^2+ \alpha^{n-1}}$

$x^n=\frac{\sigma^2}{\sigma^2+ \alpha^{n-1}}(H^Hz^n+x^{n-1})$

$z^n$ is  the  residual,$σ^2$ is  the  signal  power  and  the initialization are $z^0=0$,$x^0=0$, and $α^0=σ^2$.

it is noteworthy that  the  complexity  of  the  AMP  algorithm  is $O(nKN)$



# 討論bigO
# 模擬結果
# 討論各method優劣
# 有無更好的方法?