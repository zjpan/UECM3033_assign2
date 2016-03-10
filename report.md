UECM3033 Assignment #2 Report
========================================================

- Prepared by: **** PAN ZI JOON****
- Tutorial Group: ****T2****

--------------------------------------------------------

## Task 1 --  $LU$ Factorization or SOR method


**The reports, codes and supporting documents are to be uploaded to Github at:** 

[https://github.com/zjpan123/UECM3033_assign2](https://github.com/zjpan123/UECM3033_assign2)


**Explain your selection criteria here.**

Firstly, I would determine if the matrix A is positive definite. If the matrix A is positive define, SOR method will be used to solve the system. If matrix A is not positive definite, LU decomposition will be used to solve the system. 

This is because, according to the Convergence theorem for SOR method, suppose that matrix A has positive diagonal elements and that $$ 0 <  ω < 2, $$ the SOR method converges for any $$ x^{(0)}$$ if and only if matrix A is positive definitive. 

Therefore, I have input a few conditions to determine if the matrix is positive definite, to do that I will check for the following:
1. Strictly Diagonally Dominant Matrix
2. Positive Definite
3. Positive Diagonal Element


**Explain how you implement your `task1.py` here.**

First of all, solve(A,b) will be undergo to check the property of the matrix as the condition checking will be initialised. The condition will decide whether LU decomposition or SOR method will be used to solve the system.

In LU decomposition, scipy.linalg.lu(A) is used to decompose matrix A to P, L and U. 
$$ A = PLU , Ax = b$$ $$ Ly = b $$ $$ Ux=y$$ 
x can be calculated using the equation above.

In SOR method, optimal ω will be find by using the formula below. If matrix A is positive definite, optimal ω will be found and range of 0 < ω < 2. This ω will make the solution coverge to the solution faster.

$$ Q = \frac{1}{w}(D - wL) $$ $$ A = D-L-U $$ $$ w = \frac{2[1-{\sqrt{1-p(Kj^2)}}]}{[p(Kj)]^2} $$ where $$Kj = D^{-1}(L+U)$$

$$ X^{k+1} = Q^{-1}(Q-A)X^{k} + Q^{-1}b$$

The iteration is set to be 20. The solution will converge within 20 iterations because optimal ω is used.

The solutions to the first set of 3-variables system of linear equations are

\begin{align} x_1=1,\;\;x_2=1,\;\;x_3=1.\end{align}
for second set of 6-variables system of linear equations are \begin{align} x_1=1.0000000000000062,\;\;x_2=-0.99999999999999689,\;\;x_3=4.0,\;\;x_4=-3.4999999999999951,\;\;x_5=7.0000000000000036,\;\;x_6=-1.0000000000000004.\end{align}

---------------------------------------------------------

## Task 2 -- SVD method and image compression

Put here your picture file (Reset.png)

![Reset.jpg](Reset.jpg)

How many non zero element in $\Sigma$?

Put here your lower and better resolution pictures. Explain how you generate
these pictures from `task2.py`.

What is a sparse matrix?


-----------------------------------

<sup>last modified: change your date here</sup>
