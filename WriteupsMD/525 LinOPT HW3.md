Sam Zarr and Nick Chang

**Problem 1**
Let $A_1,\dots,A_{n}$ be a collection of vectors in $\mathbb{R}^m$.
(a) Let
$$
C=\{\sum_{i=1}^n\lambda_{i}A_{i}:\lambda_{1},\dots,\lambda_{n}\geq 0\}
$$
Show that if $y\in C$, then there exist coefficients $\lambda_{1},\dots,\lambda_{n}\geq 0$ such that (i) at most $m$ of the coefficients are nonzero, and (ii) $y=\sum_{i=1}^n\lambda_iA_i$.

We wish to show that for every $y$ within the span of these vectors there is some linear combination of the vectors that equals $y$ such that *at most m of the coefficients are nonzero*. Consider the polyhedron
$$
Q=\{(\lambda_{1},\dots,\lambda_{n})\in\mathbb{R}^n:\sum_{i=1}^n\lambda_{i}A_{i}=y,\lambda_{1},\dots,\lambda_{n}\geq 0\}
$$
First note that $Q$ is non-empty because $y\in C$. $Q$ is defined by linear inequalities and it is restricted to positive coefficients, thus it has no lines. A non-empty polyhedron with no lines must have at least one extreme point, and so $Q$ has at least one extreme point. In a standard form polyhedron the columns (vectors $A_i$) corresponding to non-zero variables of an extreme point must be linearly independent. Because the vectors $A_1,\dots,A_n$ are in $\mathbb{R}^m$ there are at most $m$ linearly independent vectors. Therefore at the extreme point there is some linear combination $\sum_{i=1}^n\lambda_{i}A_{i}=y,\lambda_{1},\dots,\lambda_{n}\geq 0$ where are most $m$ of the coefficients are non-zero. Thus we have proven that if $y\in C$ the relevant polyhedron contains an extreme point where (i) and (ii) hold as desired. 

(b) Let $P$ be the convex hull of the vectors $A_i$ in $\mathbb{R}^m$,
$$
P=\{(\sum_{i=1}^n\lambda_{i}A_{i}:\sum_{i=1}^n\lambda_{i}=1,\lambda_{1},\dots,\lambda_{n}\geq 0\}
$$
Show that if $y\in P$, then there exist coefficients $\lambda_{1},\dots,\lambda_{n}\geq 0$ with $\sum_{i=1}^n\lambda_{i}=1$, such that (i) *at most m+1* of the coefficients are nonzero, and (ii) $y=\sum_{i=1}^n\lambda_i A_i$.

$P$ is a polyhedron defined by the convex hull of the vectors $A_{i}$. As in (a) there are no lines and there must be an extreme point. We now have the constraints $\sum_{i=1}^n \lambda_{i} A_{i}=y$ and $\sum_{i=1}^n \lambda_{i}=1$.
Define $A'$ to be a new matrix such that $A_{i}'=(A_{i}, 1)$. Thus $A' \lambda=(y,1)$. At an extreme point of $P$ the columns $A_{i}'$ where $\lambda_{i}\neq 0$ must be linearly independent. Since the number of rows is $m+1$ there can only be at most $m+1$ linearly independent vectors. Therefore at this point there are coefficients $\lambda_{i}$ such that at most $m+1$ of the coefficients are nonzero. And of course this point is in $P$ so (*ii*) holds.


**Problem 2**
Consider the polyhedron $P=\{x\in\mathbb{R}^n:a_i'x\geq b_i,i=1,\dots,m\}$. Suppose that $u$ and $v$ are *distinct* basic feasible solutions that satisfy $a_i'u=a_i'v=b_i,i=1,\dots,n-1$, and assume that the vectors $a_1,\dots,a_{n-1}$ are linearly independent (this implies that $u$ and $v$ are adjacent basic feasible solutions). Let $L=\{\lambda u+(1-\lambda)v:0\leq\lambda\leq 1\}$ be the segment that joins $u$ and $v$ and let $F=\{z\in P:a_i'z=b_i,i=1,\dots,n-1\}$. Our goal is to prove that $L=F$. 
(a) Prove that $L\subseteq F$.
Consider the linear combination of $u$ and $v$: $\lambda u+(1-\lambda) v$. Then for all $i\in [1,n-1]$:
$$
\begin{align*}
a&_i'(\lambda u+(1-\lambda)v) \\
&=a_{i}'(\lambda u)+a_{i}'((1-\lambda)v) \\
&=\lambda a_{i}'(u)+(1-\lambda)a_{i}'(v) \\
&=\lambda b_{i}+(1-\lambda)b_{i} \\
&=b_{i}
\end{align*}
$$
Thus for all $z=\lambda u+(1-\lambda)v$, $z\in F$ as long as $z\in P$.
Consider now ranging over $i\in [1,m]$:
$$
\begin{align*}
a&_i'(\lambda u+(1-\lambda)v) \\
&=\lambda a_{i}'(u)+(1-\lambda)a_{i}'(v) \\
&=\lambda x+(1-\lambda)y, \ \ x,y\geq b_{i} \\
&\geq b_{i}
\end{align*}
$$
Therefore $z\in P$. And we conclude $\forall \lambda \in [0,1] \ \lambda u+(1-\lambda)v\in F$. So $L\subseteq F$.

(b) Consider the set $G=\{z\in \mathbb{R}^n : a_{i}' z=b_{i}, i=1,\dots,n-1\}$. Prove that $G$ is the line $G=\{\lambda u+(1-\lambda)v:\lambda\in \mathbb{R}\}$.
Consider an arbitrary point on the line. Using our result from (a) that for all $i=1,\dots, n-1$ and for all $\lambda \in \mathbb{R}$ $a_i'(\lambda u+(1-\lambda)v)=b_{i}$ we can confirm that the point is in the set $G$. Now we show that $z\in G$ implies $z$ is on the line. The set $G$ is the intersection of $n-1$ hyperplanes in $\mathbb{R}^n$. Since the vectors $a_1,\dots,a_{n-1}$ are linearly independent the set G is an affine subspace of dimension 1. Thus $G$ is a line. We know that $u$ and $v$ are distinct points on that line. Therefore $G$ is the line passing through $u$ and $v$: $G=\{\lambda u+(1-\lambda)v: \lambda\in \mathbb{R}\}$.

(c) Let $z\in G$. Prove that if $z\in P$ then $z\in L$.
$z$ is in $G$. Therefore $z$ is on the line $G:\{\lambda u+(1-\lambda)v: \lambda\in \mathbb{R}\}$. Assume that $z\in P$. And assume for contradiction $\lambda>1$. Then $z=\lambda u+(1-\lambda)v$. And rearranging: $u=\frac{1}{\lambda}z(1-\frac{1}{\lambda})v$. Note since $\lambda>1$ then $\frac{1}{\lambda}\in[0,1]$. Thus $u$ is a convex combination of $z$ and $v$. And we already know that $u,v,z\in P$. But $u$ is a basic feasible solution, which means it is also an extreme point. And extreme points cannot be represented as a convex combination of points in the polyhedron. We have reached a contradiction, thus our assumption $\lambda>1$ must be false.
Now assume for contradiction $\lambda<0$. Then $z=\lambda u+(1-\lambda)v$ and rearranging: $v=\frac{1}{1-\lambda}z-\frac{\lambda}{1-\lambda}u$. Since $\lambda<0$ both $\frac{1}{1-\lambda}$ and $-\frac{\lambda}{1-\lambda}$ are in the range $[0,1]$. Therefore $v$ is representable as a convex combination of $z$ and $u$ which leads to the same contradiction as the $\lambda>1$ case.
So it must be that $\lambda\in[0,1]$. And if $z$ is on the line $G$ where $\lambda\in[0,1]$ then $z$ is also in $L$.

(d) Prove that $F\subseteq L$.
Consider an arbitrary $z\in F$. Then $z\in P$ and $a_i'z=b_i,i=1,\dots,n-1$. By definition $z\in G$. Since $z\in P$ and $z\in G$ by (c) we know that $z\in L$. Since all $z\in F$ are in $L$ we have that $F\subseteq L$.


**Problem 3**
We know that every linear program can be transformed into an equivalent linear program in standard form. We also know that a nonempty polyhedron in standard form has at least one extreme point. We are then tempted to conclude that every nonempty polyhedron has at least one extreme point. What is wrong with this argument?

The issue is that an equivalent LP must have the same optimal value, but there is no requirement that it has the same extreme points. In fact, translating a problem to standard form often introduces extreme points. This extends to problems that originally have no extreme points. 
Consider the counterexample: I am a watermelon trader. We can exchange any real number of watermelons. You want to maximize the amount of money you spend, with the constraint that each watermelon costs 1 dollar to sell/buy. Let $x_1,x_2$ be watermelons bought and dollars spent respectively. Then we have the LP:
$\max x_2$
s.t $x_2=x_1$
The relevant nonempty polyhedron is a line in $\mathbb{R}^2$ with no extreme points. And translating this problem into standard form would introduce non-negativity constraints that immediately create an extreme point at $(0,0)$.


**Problem 4**
Consider the standard form polyhedron $P=\{x\in\mathbb{R}^n|Ax=b,x\geq 0\}$. Suppose that the matrix $A$, of dimension $m\times n$, has linearly independent rows, and that all basic feasible solutions are nondegenerate. Let $\bar{x}$ be a vector in $P$ that has exactly $m$ positive components. Our goal is to show that $\bar{x}$ is a basic feasible solution.
Let $B(1),...,B(m)$ be indices of the $m$ components of $\bar{x}$ that are strictly positive. By contradiction suppose that $\bar{x}$ is not a basic feasible solution.
(a) Specify which constraints are active at $\bar{x}$.
$\bar{x}$ is in $P$ so it is in $\mathbb{R}^n$ and we are assuming exactly $m$ of those components are positive. For each row $i$ in $A$ we have $A_i\bar{x}=b_{i}$. So $\bar{x}$ is fulfilling all $m$ equality constraints. The $n-m$ components of $\bar{x}$ that are not strictly positive must be zero to satisfy the non-negativity constraints. So a total of $n$ constraints are active at $\bar{x}$.

(b) Show that there exists a nonzero vector $d\in \mathbb{R}^n$ such that, for any $\epsilon\in \mathbb{R}$, all the constraints that were active at $\bar{x}$ are still active in $\bar{x}+\epsilon d$.
We are interested in constructing a nonzero vector $d$ such that $A(\bar{x}+\epsilon d)=A(\bar{x})+A(\epsilon d)=A(\bar{x})+0$. Because $\bar{x}$ is not a BFS we know there is some linear dependency among the columns $A_{B(1)},\dots,A_{B(m)}$. Therefore there exists coefficients $d_B(i)$ not all of which are zero such that $\sum_{i=1}^m d_{B(i)}A_{B(i)}=0$. Define the vector $d$ to have values $d_B(i)$ for $i\in[m]$ and have values 0 for all other components. Then we have $A(\epsilon d)=0$ for all epsilon. $d$ is nonzero and $A(\bar{x}+\epsilon d)=A(\bar{x})$ so all constraints active at $\bar{x}$ are active at $\bar{x}+\epsilon d$.

(c) Let $d$ be the vector from part (b). Prove that if $\bar{x}+\epsilon d\geq 0$ for all $\epsilon\geq 0$, then there exists an index $j\in \{B(1),\dots,B(m)\}$ such that $\bar{x}_{j}-\epsilon d_{j}<0$ for some $\epsilon>0$.
$\bar{x}+\epsilon d\geq 0$ implies that $d\geq 0$ because any negative component would push the sum negative for a large enough $\epsilon$. The result follows immediately: for all $j$ the difference $\bar{x}_{j}-\epsilon d_{j}$ is less than zero for a large enough $\epsilon$.
Another result is also useful: there exists some $\epsilon$ such that for an index $k$ we have  $\bar{x}_{k}-\epsilon d_{k}=0$ and for $j\neq k$: $\bar{x}_{j}-\epsilon d_{j}\geq 0$.

(d) Use parts (b) and (c) to find a feasible point $\tilde{x}$ with at most $m-1$ positive components and such that all the constraints that were active at $\bar{x}$ are still active at $\tilde{x}$.
Consider the vector $d$ we found in (b). If $\exists j (\bar{x_{j}}+\epsilon d_{j}\leq 0)$ then we can define $\tilde{x}=\bar{x}+\epsilon d$ and be sure that at least one of the $m$ nonzero values is not positive. And $A(\bar{x})=A(\tilde{x})$ so all the same constraints are active. Otherwise $\forall j (\bar{x}_{j}+\epsilon d_{j}\geq 0)$. We can define $\tilde{x}=\bar{x}-\epsilon d$ and by our result in (c) be sure that there exists some $\epsilon$ such that at most $m-1$ components of $\tilde{x}$ are positive. $A(\tilde{x})=A(\bar{x})$ so all active constraints at $\bar{x}$ are active at $\tilde{x}$. And each component of $\tilde{x}$ is non-negative so $\tilde{x}$ is feasible.

(e) Denote by $\ell$ the number of linearly independent active constraints in $\bar{x}$. Show that among the constraints that are active in $\tilde{x}$ there are $\ell+1$ that are linearly independent.
All $m$ equality constraints active at $\bar{x}$ are active at $\tilde{x}$. There are $n-m$ non-negativity constraints active at $\bar{x}$, all of which are active at $\tilde{x}$. In addition, there is a new equality constraint active at $\tilde{x}$. Therefore there are $m+n-m=n$ active constraints at $\bar{x}$. At $\tilde{x}$ there are $m+n-m+1=n+1$ active constraints.
Let the unit vectors corresponding to the zero components of $\bar{x}$ be $e_j$ for $\bar{x}_{j}=0$. When we consider the vector $\tilde{x}$ there is some new $e_k$ that is not zero in $\bar{x}$. To show that the rank increases to $\ell+1$ we want to show that for $\tilde{x}$ all $e_i$ are linearly independent and linearly independent from the equality constraints.
Assume for contradiction that $e_k$ is linearly dependent. Then:
$$
e_{k}=\sum_{i=1}^m f_{i}a_{i}+\sum_{j:\tilde{x}_{j}=0}g_{j}e_{j}
$$
Multiplying both sides by $d$ gives:
$$
d_{k}=\sum_{i=1}^m f_{i}(a_{i}d)+\sum_{j:\tilde{x}_{j}=0}g_{j}(e_{j}d)=0+0
$$
So $d_k=0$. But by construction $d_k\neq 0$. Therefore $e_k$ is linearly independent from the rows of $A$ and the active non-negative constraints. Therefore $\tilde{x}$ has $\ell+1$ linearly independent active constraints.

(f) Explain how to repeatedly use the previous steps to obtain a *basic feasible solution* $\tilde{x}$ with at most $m-(n-\ell)$ positive entries, whose indices are in ${B(1),\dots,B(m)}$.
If we treat $\tilde{x}$ from (d) as the new $\bar{x}$ and repeat the steps to find a new $\tilde{x}$ we can repeatedly increase the number of active linearly independent constraints. Although we cannot do this indefinitely because there are $m$ equality constraints and $n$ non-zero constraints. If $\ell=n$ then the point is a BFS. If $\ell>n$ then the point is a BFS and there is degeneracy.
Each time the process is repeated $\ell$ increases by at least 1, and the number of positive components decreases by at least 1. The original $\bar{x}$ has rank $\ell$ and $m$ positive columns. To get to a BFS we need the rank to be $n$. Thus the process needs to be repeated $n-\ell$ times. Therefore the number of positive entries at a BFS is $m-(n-l)$.

(g) Find a contradiction to conclude that $\bar{x}$ had to be a basic feasible solution.
We found that if $\bar{x}$ is not a BFS we can find a BFS with at most $m-(n-\ell)$ positive entries. And since $\bar{x}$ is not a BFS $\ell<n$ so $n-\ell\geq 1$. But in the problem statement we assumed that all basic feasible solutions are nondegenerate. But a BFS with at most $m-1$ positive entries is degenerate. Therefore we have found a contradiction. $\bar{x}$ must have been a BFS all along.


**Problem 6**
Consider the polyhedron $P$ defined by the following system of 5 linear inequalities in 3 variables $x_1,x_2,x_3$.
$$
\begin{align*}
2x_{1}-5x_{2}+4x_{3}\leq 10 \\
3x_{1}-6x_{2}+3x_{3}\leq 9 \\
5x_{1}+10x_{2}-x_{3}\leq 15 \\
-x_{1}+5x_{2}-2x_{3}\leq -7 \\
-3x_{1}+2x_{2}+6x_{3}\leq 12
\end{align*}

$$
Apply the Fourier-Motzkin elimination algorithm to $P$ to compute $\prod_1(P)$ by eliminating first variable $x_3$ and then variable $x_2$. Is $P$ empty?

We start by isolating $x_3$.
$$
\begin{align*}
-2x_{1}+5x_{2}+10\geq 4x_{3} \\
-3x_{1}+6x_{2}+9\geq 3x_{3} \\
5x_{1}+10x_{2}-15\leq x_{3} \\
-x_{1}+5x_{2}+7\leq 2x_{3} \\
3x_{1}-2x_{2}+12\geq 6x_{3}
\end{align*}
$$
And pair lower with upper bound equations:
$$
\begin{align*}
5x_{1}+10x_{2}-15\leq -x_{1}+2x_{2}+3 \\
5x_{1}+10x_{2}-15\leq -\frac{x_{1}}{2}+\frac{5x_{2}}{4}+\frac{5}{2} \\
5x_{1}+10x_{2}-15\leq \frac{x_{1}}{2}-\frac{x_{2}}{3}+2 \\
-\frac{x_{1}}{2}+\frac{5x_{2}}{2}+\frac{7}{2}\leq -x_{1}+2x_{2}+3 \\ \\
-\frac{x_{1}}{2}+\frac{5x_{2}}{2}+\frac{7}{2}\leq -\frac{x_{1}}{2}+\frac{5x_{2}}{4}+\frac{5}{2} \\
-\frac{x_{1}}{2}+\frac{5x_{2}}{2}+\frac{7}{2}\leq \frac{x_{1}}{2}-\frac{x_{2}}{3}+2 \\
\end{align*}
$$
Simplifying for $x_1$ gives:
$$
\begin{align*}
x_{1}\leq 3-\frac{4x_{2}}{3} \\
x_{1}\leq \frac{35}{11}-\frac{35x_{2}}{22} \\
x_{1}\leq \frac{34}{9}-\frac{62x_{2}}{27} \\
x_{1}\leq -x_{2}-1 \\
x_{2}\leq -\frac{4}{5} \\
x_{1}\geq \frac{17x_{2}}{6}+\frac{3}{2} \\
\end{align*}
$$
And we isolate $x_2$:
$$
\begin{align*}
3-\frac{4x_{2}}{3}\geq \frac{17x_{2}}{6}+\frac{3}{2} \\
\frac{35}{11}-\frac{35x_{2}}{22}\geq \frac{17x_{2}}{6}+\frac{3}{2} \\
\frac{34}{9}-\frac{62x_{2}}{27}\geq \frac{17x_{2}}{6}+\frac{3}{2} \\
-x_{2}-1\leq x_{2}\geq \frac{17x_{2}}{6}+\frac{3}{2} \\
\frac{17x_{2}}{6}+\frac{3}{2}\geq \frac{17x_{2}}{6}+\frac{3}{2} \\
x_{2}\leq -\frac{4}{5} \\
\end{align*}
$$
Finally solving for $x_2$:
$$
\begin{align*}
x_{2} \leq \frac{9}{25} \\
x_{2} \leq \frac{111}{292} \\
x_{2} \leq \frac{123}{277} \\
x_{2} \leq -\frac{15}{23} \\
0\leq 0 \\
x_{2} \leq -\frac{4}{5}
\end{align*}
$$
So we can see $x_2\leq-\frac{4}{5}$. Since there are valid solutions for this projection to $x_2$ there are solutions to the original problem. $P$ is nonempty. 


