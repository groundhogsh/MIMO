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


# 整理

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