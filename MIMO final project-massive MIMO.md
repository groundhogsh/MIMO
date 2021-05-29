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

[7]	X. Gao, L. Dai, C. Yuen and Y. Zhang, "Low-Complexity MMSE Signal Detection Based on Richardson Method for Large-Scale MIMO Systems," 2014 IEEE 80th Vehicular Technology Conference (VTC2014-Fall), Vancouver, BC, Canada, 2014, pp. 1-5
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6966041

[8]	M. A. M. Albreem, A. A. El-Saleh and M. Juntti, "On Approximate Matrix Inversion Methods for Massive MIMO Detectors," 2019 IEEE Wireless Communications and Networking Conference (WCNC), Marrakesh, Morocco, 2019, pp. 1-6
> https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9037579

