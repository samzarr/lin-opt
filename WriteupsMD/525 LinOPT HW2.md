**Problem 1**
Consider the optimization problem
$$
\begin{align*}
\text{minimize } &f(x) \\
\text{subject to } &x\in X\\
&\sum \limits_{j=1}^{l}\alpha\max_{i=1,\dots,k}((c^{ij})'x+d^{ij})+r'x\leq h.
\end{align*}
$$
where $f:\mathbb{R}^n\rightarrow\mathbb{R}, X\subseteq\mathbb{R}^n,\alpha_{j}\geq 0$ for all $j=1,\dots,l$, and $c^{ij}\in\mathbb{R}^n$ and $d^{ij}\in\mathbb{R}$ for all $j=1,...,l,i=1,...,k$. 
Explain how to replace (3) with $lk$ linear constraints to obtain an equivalent optimization problem with $n+l$ variables, and formally prove the equivalence.

First consider a single case of the sum in (3). We have $\alpha\max_{i=1,\dots,k}((c^{ij})'x+d^{ij})+r'x$ where $j$ is an integer $j\in [l]$. And further consider a single term of the max function, so $i$ becomes an integer $i\in[1,k]$. We have $\alpha((c^{ij})'x+d^{ij})$ #FIXME 


**Problem 2**
Consider the following problem formulation of Exercise 6 in Assignment 1.
$$
\begin{align*}
\text{maximize } &3x_{1}+3.4x_{2} \\
\text{subject to } &3x_{1}+4x_{2}\leq 20000 \\
&0.3x_{1}+0.38x_{2}\leq 4000 \\
&x_{1},x_{2}\geq 0
\end{align*}
$$
a. Solve the problem graphically to obtain an optimal solution.
![[Pasted image 20260220172731.png]]The optimal solution is at (6666.667,0). This results in a value of 20,000.

b. Suppose that the company could increase its available machine hours by 2,000, after spending $400 for certain repairs. Should the investment be made?

We can change the machine hours constrain to: $3x_1+4x_2\leq 22,000. Solving again graphicaly:
![[Pasted image 20260220173505.png]]The new optimal solution is (7333.333,0). This results in a value of 22000. The $400 investment results in $2,000 extra revenue. The investment is worth it!


**Problem 3**
Consider the following optimization problem.
$$
\begin{align*}
\text{min } &-2x_{1}+\max\{3|x_{2}-10|,x_{1}-x_{2}+1\} \\
\text{s.t. } &x_{1}+x_{2}\geq 5
\end{align*}
$$
a. Provide a linear programming reformulation of the above problem, using ideas similar to the ones discussed in class.

First we remove nonlinearity from the objective function. We can make an equivalent optimization problem:
$$
\begin{align}
\text{min } &-2x_{1}+a \\
\text{s.t. } &x_{1}+x_{2}\geq 5 \\
&a\geq \max\{3|x_{2}-10|,x_{1}-x_{2}+1\} \\
\end{align}
$$
And we can enforce the max by rewriting the third constraint as two constraints:
$$
\begin{align*}
&a\geq 3|x_{2}-10| \\
&a\geq x_{1}-x_{2}+1
\end{align*}
$$
Finally we remove the absolute value similarly by replacing the constraint with:
$$
\begin{align*}
&a\geq 3(x_{2}-10) \\
&a\geq -3(x_{2}-10)
\end{align*}
$$
So we have
$$
\begin{align}
\text{min } &-2x_{1}+a \\
\text{s.t. } &x_{1}+x_{2}\geq 5 \\
&a\geq 3(x_{2}-10) \\
&a\geq -3(x_{2}-10) \\
&a\geq x_{1}-x_{2}+1
\end{align}
$$
Finally we have to constrain all variables to the positive reals. We can do this with slack variables. Notice that constraints 2 and 3 imply $a\geq 0$. This results in an equivalent linear optimization problem.
$$
\begin{align}
\text{min } &-2(x_{1}^{+}-x_{1}^{-})+a \\
\text{s.t. } &(x_{1}^{+}-x_{1}^{-})+(x_{2}^{+}-x_{2}^{-})\geq 5 \tag{1}\\
&a\geq 3((x_{2}^{+}-x_{2}^{-})-10) \tag{2}\\
&a\geq -3((x_{2}^{+}-x_{2}^{-})-10) \tag{3}\\
&a\geq (x_{1}^{+}-x_{1}^{-})-(x_{2}^{+}-x_{2}^{-})+1 \tag{4}\\
&x_{1}^+,x_{1}^-,x_{2}^+,x_{2}^-,a\geq 0 \tag{5}
\end{align}
$$
b. Show that the original problem and the reformulation are equivalent.

We prove this by first showing that every feasible solution to the original problem has a corresponding feasible solution to the LP with no worse value. Then we show that any solution to the LP has a corresponding feasible solution to the original problem with no worse value.

First, consider an arbitrary feasible solution to the original LP $(x_1,x_2)$. Let the LP variables be: 
$$
\begin{align*}
x_{1}^+=&\max\{0,x_{1}\} \\
x_{1}^-=&\max\{0,-x_{1}\} \\
x_{2}^+=&\max\{0,x_{2}\} \\
x_{2}^-=&\max\{0,-x_{2}\} \\
a=&\max\{3|x_{2}-10|,x_{1}-x_{2}+1\}
\end{align*}
$$
Additionally, by construction we have that $x_i=x_i^+-x_i^-$ . Let's confirm that all constraints are met. By inspection we can see that each variable is non-negative so those constrains are met. Constraints 2, 3, 4 are each satisfied because $a$ is defined to be the max of the constraints. $x$ is feasible for the original problem so we have $x_1+x_2\geq 5$. By our construction this directly implies constraint 1 is satisfied.

The objective value we obtain is $-2x+a$. Substituting $a$ we have $-2x+\max\{3|x_2-10|,x_1-x_2+1\}$. This is the exact objective of the original problem. Thus we have shown that given a solution to the original problem there is a solution to the LP with equal value.

Now we show that given a solution to the LP $(x_{1}^+,x_{1}^-,x_{2}^+,x_{2}^-,a)$ we can construct a solution to the original problem with equal or less objective value. By definition we have
$$
\begin{align*}
x_{1}=&x_{1}^+-x_{1}^- \\
x_{2}=&x_{2}^+-x_{2}^- \\
\end{align*}
$$
The LP constraints are satisfied. This means that we know
$$
\begin{align*}
&x_{1}+x_{2}\geq 5 \tag{1}\\
&a\geq 3(x_{2}-10) \tag{2}\\
&a\geq -3(x_{2}-10) \tag{3}\\
&a\geq x_{1}-x_{2}+1 \tag{4}
\end{align*}
$$
Immediately we know $(x_1,x_2)$ is feasible for the original problem because (1) implies it satisfies the only constraint. 
From (2) and (3) we can see that $a\geq 3|x_2-10|$. Including (4) it must be true that $a\geq \max\{3|x_2-10|,x_1-x_2+1\}$. The LP objective function is
$$
\begin{align*}
&-2(x_1^+-x_1^-)+a \\
=&-2x_{1}+a \\
\geq& -2x_{1}+\max\{3|x_2-10|,x_1-x_2+1\}
\end{align*}
$$
The original problems objective function is exactly $-2x_{1}+\max\{3|x_2-10|,x_1-x_2+1\}$.  So we know that the LP objective function is greater than or equal to the original problems objective function.

We have shown that for every solution to the original problem there exists a solution to the LP problem with equal or lower cost. And we have shown that for every solution to the LP problem there exists a solution to the original problem with equal or lower cost. Therefore it must be that the optimal cost for both problems is the same. Thus the problems are equivalent.


**Problem 5**
Consider the polyhedron defined by the following system of linear inequalities:
$$
\begin{align*}
& x_{1} + x_{2} + x_{3} \leq 4 \tag{1}\\
& x_{1} - x_{2} \ \ \ \ \ \ \ \ \ \leq 1 \tag{2}\\
& x_{1} \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \geq 0 \tag{3}\\
& \ \ \ \ \ \ \ \ \ x_{2} \ \ \ \ \ \ \ \ \ \geq 0 \tag{4}\\
& \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ x_{3} \geq 0 \tag{5}\\
\end{align*}
$$
a. List all the basic and the basic feasible solutions of the polyhedron described above.

There are three variables so a basic solution must satisfy all equations (there are none in this problem) and be active at at least three linearly independent constraints. To find all basic solutions we enumerate through possibilities of which three equations are active. This gives 5 choose 3 (10) possibilities to consider.

If $(1),(2),(3)$ are active then $x_1=0,x_2=-1,x_3=5$. This solution is not feasible as it violates $(4)$.
If $(1),(2),(4)$ are active then $x_1=1,x_2=0,x_3=3$. This solution is feasible.
If $(1),(2),(5)$ are active then $x_1=2.5,x_2=1.5,x_3=0$. This solution is feasible.
If $(1),(3),(4)$ are active then $x_1=0,x_2=0,x_3=4$. This solution is feasible.
If $(1),(3),(5)$ are active then $x_1=0,x_2=4,x_3=0$. This solution is feasible.
If $(1),(4),(5)$ are active then $x_1=4,x_2=0,x_3=0$. This solution is not feasible as it violates $(2)$.
If $(2),(3),(4)$ are active then $x_1=?,x_2=?,x_3=?$. These constraints cannot all be active simultaneously.
If $(2),(3),(5)$ are active then $x_1=0,x_2=-1,x_3=0$. This solution is not feasible as it violates $(4)$.
If $(2),(4),(5)$ are active then $x_1=1,x_2=0,x_3=0$. This solution is feasible.
If $(3),(4),(5)$ are active then $x_1=0,x_2=0,x_3=0$. This solution is feasible.

We have found all 9 basic solutions of which 6 are feasible.

b. Consider the vector $\tilde{x}=(1,3,0)$. Is this point an extreme point of our polyhedron?

No $(1,3,0)$ is not an extreme point of the polyhedron. There are not three linearly independent constraints active at the point. Specifically, constraints (1) and (5) are active, however (2), (3), (4) hold as inequalities but not equations at the point.


**Problem 6**
Consider the polyhedron defined by the following system of linear inequalities:
$$
\begin{align*}
- x_{1} \ + x_{2} + x_{3} + 2x_{4} - 2x_{5} =& \ 1 \tag{1}\\
3x_{1} + 2x_{2} + 7x_{3} - x_{4} + 4x_{5} =& \ 7 \tag{2}\\
- 2x_{1} + 4x_{2} + 6x_{3} + 2x_{4} - x_{5} =& \ 6 \tag{3}\\
x\ \geq& \ 0 \tag{4}\\
\end{align*}
$$
Consider the three vectors $(1/2,1,1/2,0,0), (1,2,0,0,0) \text{ and } (1,0,0,1,0)$. For each vector:
a. Say if the vector is a basic solution.
b. Say if the vector is a vertex and, if so, determine an objective function that is uniquely minimized at the vertex.

Let's first note that all constraints are linearly independent. And that this is $\mathbb{R}^5$ so to be a basic solution each vector must satisfy all equations $(1), (2), (3)$ and be active at least 2 inequalities. Now consider $(1/2,1,1/2,0,0)$. All inequalities are satisfied, and the inequalities $x_4\geq 0$ and $x_5\geq 0$ are active. Now we plug into $(1),(2),(3)$ to check if the equations hold.
$$
\begin{align*}
- x_{1} \ + x_{2} + x_{3} + 2x_{4} - 2x_{5} =& -1/2+1+1/2+2*0-2*0=1\\
3x_{1} + 2x_{2} + 7x_{3} - x_{4} + 4x_{5} =& 3*1/2+2*1+7*1/2-0+4*0=7\\
- 2x_{1} + 4x_{2} + 6x_{3} + 2x_{4} - x_{5} =& -2*1/2+4*1+6*1/2+2*0-0=6
\end{align*}
$$
We find that all equations hold. Thus this is basic solution, and also a feasible solution. Because it is a basic feasible solution it is also a vertex. An objective function uniquely minimized at the vertex is $f(x):=x_{4}+x_{5}$. NVM #FIXME 


Now we consider $(1,2,0,0,0)$. All inequalities are satisfied and $x_{3}\geq 0,x_{4}\geq 0,x_{5}\geq 0$ are active. Plugging into $(1),(2),(3)$ we find that all equations hold.
$$
\begin{align*}
- x_{1} \ + x_{2} + x_{3} + 2x_{4} - 2x_{5} =& -1+2+0+2*0-2*0=1\\
3x_{1} + 2x_{2} + 7x_{3} - x_{4} + 4x_{5} =& 3*1+2*2+7*0-0+4*0=7\\
- 2x_{1} + 4x_{2} + 6x_{3} + 2x_{4} - x_{5} =& -2*1+4*2+6*0+2*0-0=6
\end{align*}
$$
Thus $(1,2,0,0,0)$ is a basic feasible solution, and also a vertex. An objective function uniquely minimized at the vertex is $f(x):=x_{3}+x_{4}+x_{5}$. We can confirm this is unique as no other solution of the form $(a,b,0,0,0)$ is feasible.


Now we consider $(1,0,0,1,0)$. Equation $(2)$ does not hold, so this is not a basic solution. Therefore this is also not a vertex. 