%% 1\.
We wish to show $f$ is a convex function, where $f(x)=\sum_{i=1}^{m}f_i(x)$ for $x\in\mathbb{R}^n$ and $(\forall i,i<m)f_i:\mathbb{R}^n\rightarrow\mathbb{R}$ is convex. Stated simply, we want to show that the linear sum of convex linear functions is also a convex function. To show $f$ is convex we show that for every $x,y\in\mathbb{R}^n$, and every $\lambda\in[0,1]$, we have $f(\lambda x+(1-\lambda)y)\leq\lambda f(x)+(1-\lambda)f(y)$.
This proof is in cases. First, take $\lambda=0$. We wish to show $f(\lambda x+(1-\lambda)y)\leq\lambda f(x)+(1-\lambda)f(y)$ which simplifies all the way to $f(y)\leq y$. Substituting the function, we wish to show $x\geq\sum_{i=1}^{m}f_i(x)$. First, notice that for all $i,f_i(x)\leq x$.
 %%
2\.
a.
We can rewrite the Linear Program as 
$\min c'x$
s.t. $Ax\geq b$
Where $c,b,A$ are defined as:
$c=(3,2,1)$
$b=(2, -2,-5,4,0,0)$
$$A=\begin{bmatrix}
1 & 1 & -1 \\
-1 & -1 & 1 \\
-1 & -2 & 0 \\
2 & 0 & -1 \\
1 & 0 & 0 \\
0 & 1 & 0
\end{bmatrix}$$
b.
We wish to convert the prior LP into the form
$\min c'x$
s.t. $Ax=b$
$x\geq 0$
Let's go through the constraints:
$x_1+x_2-x_3=2$ is already good.
$x_1+2x_2\leq 5$ can be converted by introducing a slack variable $s_1$. We write instead $x_1+2x_2+s_1=5$.
$2x_1-x_3\geq 4$ needs a slack variable as well. The new constraint is $2x_1-x_3-s_2=4$.
Finally, $x_3$ can be negative in the original formulation. We substitute $x_3=x_3^+-x_3^-$, where $x_3^+,x_3^-\geq 0$.
The standard form equivalent LP is then:
$$
\begin{align*}
\min 3x_1+2x_2+x_3^+-x_3^- \\
\text{s.t. } x_1+x_2-x_3^+-x_3^-=2 \\
x_1+2x_2+s_1=5 \\
2x_1-x_3^+-x_3^--s_2=4 \\
x_1,x_2,x_3^+,x_3^-\geq 0.
\end{align*}
$$

3.
a.
Let $t_{ij}$ be the number of exchanges of 1 of currency $i$ into $r_{ij}$ of currency $j$.
We can express how much USD is being bought by:
$$
\begin{align*}
    \sum_{i=2}^{5}t_{i1}*r_{i1}
\end{align*}
$$
We can express that no more than 100 USD can be sold through the constraint:
$$
\begin{align*}
    \sum_{j=2}^{5}t_{1j}\leq 100
\end{align*}
$$
We can express that all currencies must have non-negative balances by the constraint:
$$
\begin{align*}
    &\text{For all currencies: currency bought is greater than or equal to currency sold} \\
    &\forall k\in \{1,...,5\}:\sum_{i\in\{1,...,5\},i\neq k}t_{ik}*r_{ik}\geq \sum_{j\in\{1,...,5\},j\neq k}t_{kj}
\end{align*}
$$
We can express that profit must be no more than 5\% of USD sold with the constraint:
$$
\begin{align*}
    (\sum_{i=2}^{5}t_{i1}*r_{i1})-(\sum_{j=2}^{5}t_{1j})\leq 0.05\sum_{j=2}^{5}t_{1j}
\end{align*}
$$
b.
To ensure that all balances except USD are zero we can add the addition constraint that:
$$
\begin{align*}
    &\text{For all currencies except USD: currency bought is less than or equal to currency sold} \\
    &\forall k\in \{2,...,5\}:\sum_{i\in\{1,...,5\},i\neq k}t_{ik}*r_{ik}\leq \sum_{j\in\{1,...,5\},j\neq k}t_{kj}
\end{align*}
$$
Combined with the prior constraint that for all currencies, currency bought is greater than or equal to currency sold we can be sure that for all currencies except USD, currency bought is exactly equal to currency sold. 
c.
To prove that this problem is feasible and the solution is non-negative we can simply provide an example exchange that meets these criteria. Consider the exchange: $1 \text{USD} \rightarrow 0.82145 \text{GBP} \rightarrow 1.00010716 \text{USD}$. The total USD sold is 1, making the objective function take a positive value. Lets check the constraints hold. Less than 100 USD were sold (1 was). The balance of all currencies except the US are zero.  The balance of the US is 1.00010716. The profit in USD is far less than $5\%$ of USD sold ($0.00010716<1*5\%$). Thus the problem is feasible and the optimal cost is non-negative.

d.
Our goal is to buy as much USD as possible. If it is possible to gain arbitrary profit than we could make an arbitrary amount of money and use that to buy USD. The function we are maximizing would go to infinity. The same thing would happen if we removed the cap on the amount of USD we can sell. If we could sell USD and then buy it right back then even breaking even on such a deal would allow an infinite amount of USD to be bought (and sold).

4.
Given a single roll, there are only ten ways to divide that roll into smaller rolls of size 25, 30, and 35 without leaving enough remaining roll to make anything. Let $x_i$ represent the ith method of cutting.
$$
\begin{align*}
&x_1:=(4*25),x_2:=(3*25,1*30),x_3:=(1*25,1*30,1*35), \\
&x_4:=(2*25,1*35),x_5:=(1*25,2*30),x_6:=(1*25,2*35), \\
&x_7:=(3*30),x_8:=(2*30,1*35),x_9:=(1*30,2*35),x_{10}:=(3*35)
\end{align*}
$$
Define $a,b,c$ to be the number of rolls produced of width 25, 30, and 35 respectively.
$a=4x_1+3x_2+x_3+2x_4+x_5+x_6$
$b=x_2+x_3+2x_5+3x_7+2x_8+x_9$
$c=x_3+x_4+2x_6+x_8+2x_9+3x_{10}$
The total waste is the total paper used minus the paper ordered. $W=105L\sum_{i=1}^{10} x_i-(100*25L+125*30L+80*35L)=105L\sum_{i=1}^{10} x_i-9050L$
We are looking to minimize $W$ so it is as effective to minimize $Z=\sum_{i=1}^{10} x_i$.
We can express this as the following linear program:
Minimize $Z$,
Subject to:
$a\geq 100$
$b\geq 125$
$c\geq 80$
$x_i\geq 0, \forall i\in\{1,...,10\}$
And each of $x_i$ must be an integer.

%% 5 %%.


6.
$x:=$ first product produced. $y:=$ second product produced. $z:=$ available cash.
For the machine hours we have $3x+4y\leq 20,000$
And for the available cash we have $3x+2y\leq z$ where $z=4,000+6x*.45+5.4y*.3=2.7x+1.62y$
The total revenue is $6x+5.4y$. And the total production cost is $3x+2y$. Thus the net income is $3x+3.4y$.
Formatting this as a linear programming problem:
Maximize $f(x,y)$ where $f(x,y)=3x+3.4y$
Subject to:
$3x+4y\leq 20,000$
$0.3x+0.38y\leq 4000$
$x,y\geq 0$
