**Problem 1**
Let $P=\{x\in \mathbb{R}^3|x_{1}+x_{2}+x_{3}=1,x\geq 0\}$ and consider the vector $x=(0,0,1)$. Find the set of feasible directions at $x$.

The set of feasible directions at $x$ are all directions $d\in \mathbb{R}^3$ such that $d_{1}+d_{2}+d_{3}=0$ and $x_i+d_i\geq 0$ for all $i\in \{1,2,3\}$. For $x=(0,0,1)$ we must have that $d_1,d_2\geq 0$. Therefore the set of directions $D$ is $\{d \in \mathbb{R}^3 | d_{1}+d_{2}+d_{3}=0,d_{1},d_{2}\geq 0\}$


**Problem 2**
Consider the LP problem
$$
\begin{align*}
\text{minimize } \ &2x_{1}+x_{2}-x_{3}-2x_{4} \\
\text{subject to } \ &x_{1}+x_{2}+3x_{3}+x_{4}=4 \\
&2x_{2}+2x_{3}-3x_{4}=4 \\
&x_{1},x_{2},x_{3},x_{4}\geq 0.
\end{align*}
$$
(a) Can we choose $x_1$ and $x_2$ as basic variables? If so, what if is the corresponding basis matrix $B$ and basic feasible solution $x^*$?
Choosing $x_1$ and $x_2$ as basic variables and setting $x_3,x_{4}=0$ leaves us with the constraints: $x_1+x_2=4$ and $2x_2=4$ and $x_1,x_2\geq 0$. Thus $x_2=2$ and $x_1=2$. The resulting basic feasible solution is $x^*=(2,2,0,0)$. The basis matrix $B$ is:

| 1   | 1   |
| --- | --- |
| 0   | 2   |
(b) Construct the 3rd basic feasible direction $d$ and calculate the reduced cost of $x_3$. Is $x^*$ optimal?
The third basic feasible direction $d$ corresponds to increasing $x_3$ to a positive value while maintaining the basis $x_1,x_2$. We are constructing $x^*+\theta d$ where $d=(0,0,1,0)$. We can calculate $Bd_B=-A_3$ so $((1, 1),(0, 2))(d_1,d_2)=-(3,2)$. So $d_1+d_2=-3$ and $2d_2=-2$. Therefore $d_2=-1$ and $d_1=-2$. Thus the third basic feasible direction is $d=(-2,-1,1,0)$. Let us test the cost of $x^*+\theta d$. The cost of $x^*$ is $4+2=6$. The cost of $\theta d$ is $\theta(-4-1-1)=-6\theta$. Therefore moving in this direction reduces the cost and $x^*$ is not optimal.

(c) Find a new basic feasible solution $y$ using the 3rd basic feasible direction $d$, and determine if $y$ is optimal.
We are interested in a point $y=x^*+\theta d$ where either $x_1=0$ or $x_2=0$. We have $x_1=2-2\theta$ and $x_{2}=2-\theta$. We can see that $x_1=0$ when $\theta=1$. So $y=x^*+1d$. So $y=(2-2,2-1,0+1,0)=(0,1,1,0)$. We can determine whether this $y$ is optimal by checking whether any feasible direction results in a better value. We already know the first basic direction is not a good choice so we need only check the fourth basic direction. We construct $d'=(0,0,0,1)$ where the basic matrix is:

| 1   | 3   |
| --- | --- |
| 2   | 2   |
And we wish to solve $Bd_{B}=-A_{4}$. So $((1,3),(2,2))(d_2,d_3)=(-1,3)$. We have $d_{2}+3d_{3}=-1$ and $2d_{2}+2d_{3}=3$. Thus $d_2=\frac{11}{4}$ and $d_3=-\frac{5}{4}$. So $d=(0,\frac{11}{4},-\frac{5}{4},1)$. We find that the value of $\theta d=\theta(\frac{11}{4}+\frac{5}{4}-2)=2\theta$. Therefore moving in the direction of $d$ raises the cost. So $y$ is optimal.


**Problem 3**
Let $x$ be a basic feasible solution associated with some basis matrix $B$. Prove the following:
(a) If the reduced cost of every nonbasic variable is positive, then $x$ is the unique optimal solution.
We use a proof by contrapositive. Assume that $x$ is not a unique optimal solution. Then because the LP is convex there is some direction $d$ such that cost of $x+\theta d$ is less than or equal to the cost of $x$. Further, there is some such $d$ that is a basic direction. If moving along a basic direction does not increase the cost of the solution then the reduced cost associated with that variable is not positive. Therefore there is some nonbasic variable with non-positive reduced cost.

(b) If $x$ is the unique optimal solution and is nondegenerate, then the reduced cost of every nonbasic variable is positive.
Consider moving in the basic direction $d$ associated with an arbitrary nonbasic variable. Then we have the point $x+\theta d$ for some positive $\theta$. Because $x$ is the unique optimal solution the cost at this point is greater than the cost at $x$. Therefore moving in the direction $\theta d$ results in increased cost. Therefore the cost of this nonbasic variable is positive. Because the choice of nonbasic variable was arbitrary this is true of all nonbasic variables.


**Problem 4**
Consider the problem of minimizing $c'x$ over the set $P=\{x \in \mathbb{R}^n: Ax=b, Dx\leq f, Ex\leq g\}$. Let $x^*\in P$ be such that $Dx^*=f, (Ex^*)_{i}<g_{i}$ for all $i$. Show that the set of feasible directions at $x^*$ is $\{d\in \mathbb{R}^n:Ad=0,Dd\leq 0\}$.

Let $F$ be the set of feasible directions at $x^*$ and let the set $S$ be $\{d\in \mathbb{R}^n:Ad=0,Dd\leq 0\}$. We wish to show that $F=S$.
First we show that $F\subseteq S$. Let $d\in F$ be an arbitrary feasible direction at $x^*$. That is $x^*+\theta d\in P$ for a scalar $\theta>0$. Then by the properties of feasible directions we have $Ad=0$. And we have $D(x^*+\theta d)\leq f$. Expanding we get $Dx^*+\theta Dd\leq f$. These constraints are active at $x^*$ so $Dx^*=f$. Therefore $f+\theta Dd\leq f$ and since $\theta>0$ it must be that $Dd\leq 0$. Since both $Ad=0$ and $Dd\leq 0$ it must be that $d\in S$. Therefore $F\subseteq S$.

Next we show that $S \subseteq F$. Suppose we have an arbitrary direction $d\in S$. We have $Ad=0$ and $Dd\leq 0$. We can show that $d\in F$ by finding $\theta>0$ such that $x^*+ \theta d \in P$. To find such a $\theta$ we must have the various constraints hold: $A(x^*+\theta d)=Ax^*+\theta Ad=b$. So $\theta\geq 0$. And $D(x^*+\theta d)=Dx^*+\theta Dd=f+\theta Dd$. Since $Dd\leq 0$ we know $f+\theta Dd\leq f$. So again $\theta\geq 0$. Finally it must be that $E(x^*+\theta d)\leq g$ so $Ex^*+\theta Ed\leq g$. We know that $(Ex^*)_{i}<g_{i}$ for all rows $i$. Therefore we have the constraint $\theta(Ed)_{i}\leq g_{i}-(Ex^*)_{i}$. So $\theta\leq \frac{g_{i}-(Ex^*)_{i}}{(Ed)_{i}}$. The numerator is always positive for any $i$. We can see that this constraint is satisfied for some $\theta'=\min_{i}\frac{g_{i}-(Ex^*)_{i}}{(Ed)_{i}}$. Thus all constraints are satisfied and we find that $d$ is a feasible direction, so $d\in F$ and $S\subseteq F$.

We have shown that $F\subseteq S$ and $S\subseteq F$. Therefore $F=S$. And so we have that the set of feasible direction at $x^*$ is $\{d\in \mathbb{R}^n:Ad=0,Dd\leq 0\}$.


**Problem 5**
Consider a feasible solution $x$ to the standard form problem
$$
\begin{align*}
\text{minimize } \ &c'x \ \ \ \ \ \ \ \ \ \ \ (1)\\
\text{subject to } \ &Ax=b \\
&x\geq 0,
\end{align*}
$$
and let $Z=\{i:x_i=0\}$. Show that $x$ is an optimal solution if and only if the linear programming problem
$$
\begin{align*}
\text{minimize } \ &c'd  \ \ \ \ \ \ \ \ \ \ \ (2)\\
\text{subject to } \ &Ad=0 \\
&d_{i}\geq 0, \ i\in Z,
\end{align*}
$$
has an optimal cost of zero.


First assume that $x\in \mathbb{R}^n$ is an optimal solution to problem (1). We wish to show the second problem has optimal cost of zero. Let $d$ be any arbitrary feasible solution to problem (2). $d$ satisfies (2), therefore we have $Ad=0$ and $d_i\geq 0 \text{ for all }i\in Z$. Assume for contradiction that the optimal cost for (2) is not zero, that is for optimal $d$: $c'd\neq 0$.

Case 1: $c'd<0$. Then we can construct a new solution $y=x+\theta d$ for scalar $\theta>0$. We have that $Ay=A(x+\theta d)=Ax+A\theta d=Ax+0=b$. And $x\geq 0$ also holds. The cost $c'y=c'(x+\theta d)=c'x+\theta c'd$. Since $\theta$ is a positive constant and $c'd<0$ then the solution $c'y$ has lower value than $c'x$. But this is a contradiction because $x$ is optimal. Therefore the assumption $c'd<0$ can not be true.
Case 2: $c'd>0$. Consider the vector $d^*=0$. This fulfills all the constraints of (2) easily. Yet, $c'd^*=0$. Which is a contradiction with the assumption that $c'd>0$. Therefore this assumption is false.
By contradiction we have proven that it must be that the optimal cost for (2) is zero.

Now we prove that if (2) has optimal cost zero then $x$ is an optimal solution. We have by assumption that for every feasible direction $d$ we have $c'd\geq 0$. Consider an arbitrary feasible solution to (1) $y$. So $Ay=b$ and $y\geq 0$. Consider the difference vector $d=y-x$. We claim this is a valid direction for (2). The equality constraints are: $Ad=Ay-Ax$. Since both $x$ and $y$ are feasible we know $Ay-Ax=b-b=0$. For the non-negativity constraints: where $i\in Z$ we know $x_i=0$. Since $y$ is feasible we have $y_i\geq 0$. So $d_i=d_i-x_i=y_i-0=y_i\geq 0$. So we have confirmed $d=y-x$ satisfies the constraints of (2). So we know $c'd\geq 0$. So $c'(y-x)\geq 0$. And simplifying we have $c'y\geq x$. Therefore $x$ must be an optimal solution.

We have shown both directions, completing the proof.