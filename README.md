UECM3033 Numerical Methods (Assignment #2)
========================================================
--------------------------------------------------------

DEADLINES:

 - This assignment will contribute to 5 marks of the coursework.
 - Assignment submission: 29/1/2016 (Friday) by 12:00 noon.
 - Peer Reviews: 5/2/2016 (Friday) by 12:00 noon.

**All deadlines are final and no extensions are allowed.** Delay in submission of the assigments will delays the peer review process. Thus a penalty of 1 mark per day will be imposed for one day late in submission of assignment. Each student will need to review two peers. No mark will be awarded if a student failed to review the two peers.

You could always edit and change your submission as many time as you like. However, you are not suppose to change your submission when the peer reviews starts. Your reviewers will be asked to check the last modified dates of your files. If the dates is beyond the stipulated due dates, you will be considered as late submission and same penalty will be applied.

---------------------------------------------------------
There are a total of 2 tasks for this assignments:

- Implement conjugate gradient methods to solve a linear system
- Application of SVD in image compression

---------------------------------------------------------

## Task 1 -- Conjugate gradient method

In this task, you will write a `Python` code to implement the conjugate gradient method to solve systems of linear equations. Later, your implementation of the conjugate gradient will be subjected to an automated computer assessment script. The number of linear systems that it passes will give you the score for this part of the assignment.


##### 1. Clone the repository
```
$ git clone https://github.com/your_github_id/UECM3033_assign2
```
This will create a *```UECM3033_assign2```* folder. In your *`UECM3033_assign2`* folder, there will be `task1.py` file.

##### 2. Edit `task1.py`.
Replace the commented block in the `conjgrad` function with your implementation of conjugate gradient method. 

Note: **DO NOT** change the `def` line and the `return` line in `task1.py`, also **DO NOT** change the name of `task1.py`. Changing these will caused the computer assessment script fail to run and hence your implementation considered as failed the automated tests.

##### 3. Report write up
Write a short description on how you implement the conjugate gradient method. You can use the given template in markdown language `report.md`, or create your own doc report.

##### 4. Commit changes and push your completed `task1.py` and report to Github.

##### 5. Review submissions from your peers.
Run the `test_task1.py` and evaluate the code in `task1.py`. Fill in the google form. 

------------------------------------------------------------

## Task 2 -- SVD method and image compression

One of most useful results from linear algebra is the singular value decomposition SVD. In this task, we will be demonstrating the application of SVD in image compression.

(As Github markdown doesn't render equations well, you can see the [`README.html`](README.html))

We will briefly discuss SVD here. We already know that a square matrix *A* is *diagonalisable* if we can write it as 

$${A} = {PDP}^{-1}.$$

Here 

\begin{align*}
D =  \left[ \begin{array}{ccc}
    \lambda_1 & 0 & \dots & 0\\
    0 & \lambda_2 &  \dots & 0 \\
    \vdots & \dots & \ddots & \vdots\\
    0 & 0 & \dots & \lambda_n
    \end{array} \right],
\end{align*}

and $$P = [v_1, v_2, \dots, v_n],$$

where $ v_i $  and  are the eigenvalues and eigenvectors. Singular value decomposition is essentially generalize this diagonalisation to non-square matrix.


For any matrix is symmetric. Symmetric matrix has a nice property of its eigenvectors form an orthonormal basis.

------------------------------------------------------------

## Summary:

### Task 1:
* clone UECM3033_assign1 repository
* pull repository
* submit screen shot "python.png" to Github

### Task 2:
* Edit and modify ```pyexercise.py```
* Edit and modify ```report.md```
* Submit ```pyexercise.py``` and ```report.md``` to Github.

-----------------------------------

<sup>last modified: 22 Dec 2015</sup>
