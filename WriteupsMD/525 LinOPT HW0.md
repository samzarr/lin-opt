1. 
a. $((\forall x\in\mathbb{Z})\exists k\in\mathbb{Z})2x=2k$ 
b. $(\exists x,y)x=2y+1\rightarrow (\exists k\in\mathbb{Z})x=2k+1$ 
c. $(\forall S\subset\{1,2,3,4,5,6,7,8\})|S|\geq5\rightarrow(\exists x\in S,\exists k\in\mathbb{Z})x=2k$ 

2. 
a. There is a student of 525 who is less than 22 years old. 
b. There is some math class containing no student who is a genius. 
c. In some lecture the teacher arrives on time. 

3. 
a. sufficient but not necessary 
b. necessary but not sufficient 

4. 
a. A is sufficient for B 
b. B is sufficient for A 

5. 
Card one to make sure the opposite is 5. Card two to make sure the opposite is not A. Card three to make sure the opposite is not A. Card four need not be flipped. 

6. 
a. Counterexample: 3. 
b. Counterexample: $\{1,5,7\}$. 
c. Counterexample: Imagine the 5 people sitting in a circle, and each knows only their neighbors. 

7. 
a. $(\exists k\in\mathbb{Z}) x=2k$ And $xy=2ky$. $k\times y$ is an integer by closure. So $(\exists m\in\mathbb{Z})2ky=2m$. Thus $xy$ is even. 
b. Either $x$ or $x+1$ is even. An integer times an integer where at least one is even results in an even number. Therefore $x(x+1)$ is even. 

8. 
$x$ is odd so $(\exists k\in\mathbb{Z})x=2k+1$. We want to show $(\exists y\in\mathbb{Z})(2k+1)^2=8y+1$. 
Expanding: 
$$(\exists y\in\mathbb{Z})4k^2+4k+1=8y+1$$ 
Simplifying: 
$$(\exists y\in\mathbb{Z})k(k+1)=2y$$ 
Using our result from 7 we know the LHS is even. The RHS which can range over any even number can therefore be set equal in all cases. 

9. 
AFC $\sqrt{2}+\sqrt{6}\geq\sqrt{15}$. Squaring both sides gives: 
$$2+6+2\sqrt2\sqrt6\geq 15$$ 
Which simplifies to $4\sqrt{3}\geq 7$. Squaring both sides again: 
$$16 \times 3 \geq 49$$ 
So $48 \geq 49$. But this is a contradiction. So the original assumption is false and $\sqrt{2}+\sqrt{6}<\sqrt{15}$.

10. 
Want to prove for an integer $x$ if $x^2$ is odd then $x$ is odd. We instead prove $x^2$ is even implies $x$ is even. 

11. 
We prove by induction that $((\forall x\in\mathbb{N})\exists k\in\mathbb{Z})2^{3x+1}+5=7k$. 
Base case $x=0$. 
$2^{3(0)+1}+5=2^1+5=7$. Setting $k=1$ makes RHS $=7$. So the statement holds in the base case. 
Inductive step $x=m+1$ assuming holds for $x=m$. 
$$2^{3(m+1)+1}+5=2^{3m+4}+5=8(2^{3m+1})+5$$ 
By IH we know $2^{3m+1}=7k-5$ for some $k$. Plugging into the LHS we need only show $8(7k-5)+5$ is a multiple of $7$. 
Simplifying: 
$$8(7k-5)+5=56k-35$$ 
$56k-35$ is divisible by seven so we have proved LHS=RHS in the inductive case. 
This completes the inductive proof that LHS=RHS for all positive integers. 

12. 
We prove by induction on $n$ that $\sum_{k=1}^nk(k+1)=\frac{n(n+1)(n+2)}{3}$. Our inductive hypothesis is that if the statement proves true for $n=m$ where $m$ is some integer, then the statement holds true for $n=m+1$. 
Base case $n=1$. 
$$\sum_{k=1}^nk(k+1)=\sum_{k=1}^1k(k+1)=2$$ 
$$\frac{n(n+1)(n+2)}{3}=\frac{1(2)(3)}{3}=2$$ 
Inductive case $n=m+1$. 
We want to prove that $\sum_{k=1}^{m+1}k(k+1)=\frac{(m+1)(m+2)(m+3)}{3}$. 
By IH we know the statement holds true for $n=m$ so $\sum_{k=1}^mk(k+1)=\frac{m(m+1)(m+2)}{3}$. 
Notice:
$$\sum_{k=1}^{m+1}k(k+1)=(m+1)(m+2)+\sum_{k=1}^mk(k+1)=(m+1)(m+2)+\frac{m(m+1)(m+2)}{3}$$ 
Factoring we find: $(m+1)(m+2)(1+m/3)$. And simplifying: $\frac{(m+1)(m+2)(m+3)}{3}$. We have proven that the LHS equals the RHS in the inductive case. 
By induction we have shown that the equality holds for all integers $n$ greater than or equal to $1$. 

13. 
a. $AB=\begin{bmatrix} 26 & 34 & 24 \\ 45 & 57 & 19 \\ 79 & 65 & 69 \end{bmatrix}$ 
b. $AB=\begin{bmatrix} 31 \end{bmatrix}$ 
c. $AB=\begin{bmatrix} 8 & 4 \\ 6 & 10 \end{bmatrix}$ 
d. $AB$ does not exist. 

14. 
a. $x'y=3+12-15=0$ and $x'z=6+4-5=5$ 
b. Yes $x$ and $y$ are orthogonal. $x$ and $z$ are not orthogonal. 
c. $x$: $\sqrt{9+16+25}=\sqrt{50}$. $y$: $\sqrt{1+9+9}=\sqrt{19}$. $z$: $\sqrt{4+1+1}=\sqrt{6}$. 

15. 
a. True. The RHS is maximized when the $x'$ and $y$ are parallel, and is equal to the LHS. 
b. True. Positive values are squared. Negative values are also squared. The result is a sum of positive numbers. 
c. False. Matrix multiplication is not commutative. 
d. 

16. 
a. Yes it is invertible. 
$$A^{-1}=\begin{bmatrix} 1/6 & 1/6 & -1/2 \\ 2/3 & -1/3 & 1 \\ 1/6 & 1/6 & 1/2 \end{bmatrix}$$ 
Find all solutions of the system $Ax=b$ for $b=(2,1,1)$. 
To solve we multiply both sides by $A^{-1}$. $x=A^{-1}b$. 
$$x=\begin{bmatrix} 1/6 & 1/6 & -1/2 \\ 2/3 & -1/3 & 1 \\ 1/6 & 1/6 & 1/2 \end{bmatrix}\begin{bmatrix} 2 \\ 1 \\ 1 \end{bmatrix}=\begin{bmatrix} 0 \\ 2 \\ 1 \end{bmatrix}$$ 

17. 

18. 
a. yes they are linearly independent 
b. $z=x+y$. So $z=(-10,1,1,5)$. 
c. No they are not. $z=x+y$. 

19. 
Take the second definition, $f(x)=c_1x+c_2x+...+c_nx$. 
First we show $f(ax)=af(x)$ for constant $a$. 
$$f(ax)=c_1(ax)+c_2(ax)+...+c_n(ax)=a(c_1x)+a(c_2x)+...+a(c_nx)=a(c_1x+c_2x+...+c_nx)=af(x)$$ 
Next we show $f(x+b)=f(x)+f(b)$ for constant $b$. 
$$
\begin{aligned}
f(x+b) &= c_1(x+b)+c_2(x+b)+...+c_n(x+b) \\
&= c_1x+c_1b+c_2x+c_2b+...+c_nx+c_nb \\
&= (c_1x+c_2x+...+c_nx)+(c_1b+c_2b+...+c_nb) \\
&= f(x)+f(b)
\end{aligned}
$$
