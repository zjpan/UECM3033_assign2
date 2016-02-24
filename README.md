UECM3033 Numerical Methods (Assignment #2)
========================================================
--------------------------------------------------------

DEADLINES:

 - This assignment will contribute to 5 marks of the coursework.
 - Assignment submission: 11/3/2016 (Friday) by 12:00 noon.
 - Peer Reviews: 18/3/2016 (Friday) by 12:00 noon.

**All deadlines are final and no extensions are allowed.** Delay in submission of the assigments will delays the peer review process. Thus a penalty of 1 mark per day will be imposed for one day late in submission of assignment. Each student will need to review two peers. No mark will be awarded if a student failed to review the two peers.

You could always edit and change your submission as many time as you like. However, you are not suppose to change your submission when the peer reviews starts. Your reviewers will be asked to check the last modified dates of your files. If the dates is beyond the stipulated due dates, you will be considered as late submission and same penalty will be applied.

---------------------------------------------------------
There are a total of 2 tasks for this assignments:

- Solve linear systems
- Application of SVD in image compression

#### General comments:
* Login to your GitHub. (If you have forgotten how to do that, please refer to Assignment #1)
* While still stay logged in GitHub, go to [https://github.com/yongkheng/UECM3763_assign2](https://github.com/yongkheng/UECM3033_assign2)
* Click "fork" button at the top right hand corner. Now your GitHub will have a copy of the UECM3033_assign2 repository. Copy the URL.
* Go to the google form [http://goo.gl/forms/mjxWOazoJT](http://goo.gl/forms/mjxWOazoJT).
* Fill in your name, ID and the URL to your newly forked repository.
* Answer the question in the google form and submit.
* Clone the repository to your PC.

---------------------------------------------------------

## Task 1 -- $LU$ Factorization or SOR method

You are given the following two linear systems:

~~ Math
\begin{bmatrix}
   2& 1& 6 \\
   8& 3& 2 \\
   1& 5& 1
\end{bmatrix}
\begin{bmatrix}
 x_1 \\ x_2 \\ x_3
\end{bmatrix}=
\begin{bmatrix}
    9 \\ 13\\ 7
\end{bmatrix}
~~

and

~~ Math
\begin{bmatrix}
   6566& -5202& -4040& -5224& 1420& 6229 \\
   4104& 7449& -2518& -4588& -8841& 4040\\
   5266& -4008& 6803& -4702& 1240& 5060\\
   -9306& 7213& 5723& 7961& -1981& -8834\\
   -3782& 3840& 2464& -8389& 9781& -3334\\
   -6903& 5610& 4306& 5548& -1380& 3539
\end{bmatrix}
\begin{bmatrix}
 x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5 \\ x_6
\end{bmatrix}=
\begin{bmatrix}
    17603\\  -63286\\   56563\\  -26523.5\\ 103396.5\\ -27906
\end{bmatrix} .
~~

In this task, you will write a `Python` code to implement the
$LU$ method and SOR method to solve systems of linear equations.

##### 1. Clone the repository
```
$ git clone https://github.com/goh.yongkheng/UECM3033_assign2
```
This will create a *```UECM3033_assign2```* folder. In your *`UECM3033_assign2`* folder, there will be `task1.py` file.

##### 2. Edit `task1.py` - implement `lu` and `sor`
In `task1.py`, implement the $LU$ method and SOR method to solve a linear system $A x = b$. The function `lu` and `sor` take two inputs: `A` is a 2-d list of shape $(n,n)$ and `b` is a list of length $n$. The functions return a list of length $n$ `sol` with is the solution of the linear system.

For the `sor` function, you will need to include the estimation of a good value of $\omega$ which gives quick convergent rate.

##### 3. `lu` or `sor`?

Now you have implemented the $LU$ method and the SOR method, the next question is which method to use?

Explain in your report under what scenario `lu` is preferred method for solving linear system. Do the same for `sor`.

Then, put translate the scenario that you explain in your report into the selection criteria in your `Python` program. Edit the line 
```
condition = True # State and implement your condition here
```
in the definition of `solve`.

##### 4. Test your `lu`, `sor` and `solve` functions

Test your implementation of the functions. Report the answers for the above two linear systems. Explain how you check the answers.

Later, your implementation will be subjected to an automated computer assessment script. The number of linear systems that it passes will contribute to the score for this part of the assignment.

Note: **DO NOT** change the `def` line and the `return` line in `task1.py`, also **DO NOT** change the name of `task1.py`. **DO NOT** change the 
```
## import checker
## checker.test()
```

Changing these will caused the computer assessment script fail to run and hence your implementation considered as failed the automated tests.

##### 5. Report write up
Write a short description on how you implement `task1.py`. You can use the given template in markdown language `report.md`, or create your own doc report.

##### 6. Commit changes and push your completed `task1.py` and report to Github.

------------------------------------------------------------

## Task 2 -- SVD method and image compression

One of most useful results from linear algebra is the singular value decomposition SVD. In this task, we will be demonstrating the application of SVD in image compression.

We will briefly discuss SVD here. We already know that a square matrix *A* is *diagonalisable* if we can write it as

~~ Math
{A} = {PDP}^{-1}.
~~

Here 

~~ Math
D =  \begin{bmatrix}
    \lambda_1 & 0 & \dots & 0\\
    0 & \lambda_2 &  \dots & 0 \\
    \vdots & \dots & \ddots & \vdots\\
    0 & 0 & \dots & \lambda_n
    \end{bmatrix},
~~

and $P = [v_1, v_2, \dots, v_n],$

where $\lambda_i$ and $ v_i $  and  are the eigenvalues and eigenvectors.
Singular value decomposition is essentially generalize this diagonalisation to non-square matrix.

For any matrix $A$, $A^T A$ is symmetric. A symmetric matrix has a nice property of its eigenvectors form an orthonormal basis, i.e. $v_i^T v_j = \delta_{ij}$, where $\delta_{ij}$ is 1 if $i=j$ and 0 otherwise.

Let define another two variables, $\sigma_i = \sqrt{\lambda_i}$ and $r_i = \frac{Av_i}{\sigma_i}$. $\sigma_i$ is called **singular value**. Then, any $N\times M$ matrix $A$ can be written as 

~~ Math
A =U\Sigma V^T,
~~

where 

- $\Sigma$ is a $N \times M$ matrix with diagonal terms are $\sigma_n$ and padded with zeros if out of $\sigma$.
-  $U$ is $N \times N$ matrix with $r_i$ as columns.
-  $V$ is $M \times M$ matrix with $v_i$ as columns.

In Python, you can compute $\Sigma, U$ and $V$ quickly by using `scipy.linalg` package. You are to use SVD to do image compression.

##### 1. Loading a picture file

A color picture file (tiff or jpg file) is essentially a collection of 3 matrices: one matrix each for the red, green and blue colours. In the `UECM3033_assign2` folder, there is a picture file `lenna.tiff`, and a `Python` code `task2.py`. The `Python` code will load (`imread`), split into 3 matrices for red, green and blue components, and finally display (`imshow`) the picture file and the 3 components. 

In this task you choose your own picture file with approximately $1000 \times 800$ pixels. (Your picture should not be square.) Modify `task2.py` and save the picture into your report. You also need to submit your picture file to your github as well.

##### 2. Singular Value Decomposition

Extend your `task2.py` so that for each of the red, green and blue matrices, decompose into another 3 matrices $\Sigma, U$ and $V$. Use suitable names for your matrices and use comment to label them.

How many none zero elements in $\Sigma$?

##### 3. Compress - Lower resolution picture

Now, consider $\Sigma, U$ and $V$ created from the red matrix. 

- Create a new matrix $\Sigma_{30}$ which is the same dimensions as $\Sigma$, but keeping the first **30** none zero elements as in $\Sigma$, and set all other none zero elements to zero.
- Construct the lower resolution matrix $r_{30} = U \Sigma_{30} V^T$.

Repeat the process for green and blue matrices. Finally, create a colour picture from the 3 components and display.

##### 4. Compress - better resolution picture

Create a better resolution color picture by repeating the same procedure as previously, but this time keep the first **200** none zero elements rather than 30.

##### 5. Discussion

Go to library or otherwise, find out what is a sparse matrix? Can you relate how the sparse matrices are used here in image compression with SVD?

##### 6. Report write up
Write a short description on how you implement `task2.py`. You can use the given template in markdown language `report.md`, or create your own doc report.

##### 7. Commit changes and push your completed `task2.py`, your picture file, and report to Github.

------------------------------------------------------------

## Summary:

### Task 1:
* clone UECM3033_assign2 repository
* Edit and submit `task1.py` to Github
* Report your findings and explanation in `report.md` or `report.doc`

### Task 2:
* Edit and submit ```task2.py``` to Github
* Submit the picture file you use for this task to Github.
* Report and submit your findings in `report.md` or `report.doc` to Github.
 (you can use the same file for the Task 1 and Task 2.)

-----------------------------------

<sup>last modified: 22 Feb 2015</sup>
