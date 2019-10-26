---
title: Two Movies
---

> You have a database with a countably infinite number of movies.
Each movie has a rating that is uniformly distributed in
$$ \{ 0, 1, 2, 3, 4, 5 \} $$ and you want to find two movies such that
the sum of their ratings is greater than $$ 7.5 $$.
Your strategy for choosing the movies is as follows:
you select one movie at a time, keeping only the movie with
the highest rating so far. You stop when the sum of the ratings of
the most recent movie selected and the movie with the highest rating
of all previous movies is greater than $$ 7.5 $$.  
> Define an appropriate Markov chain and find the
expected number of movies you will need to select.

Let $$ X_n $$ be the value of the highest rating chosen after
$$ n $$ selections, without having terminated the process.
Let's also add a state $$ \Omega $$ to our Markov chain
to denote when our sum exceeds $$ 7.5 $$,
so our state space $$ \mathcal{X} = \{ 0, 1, 2, 3, 4, 5, \Omega \} $$.
If we define $$ \beta(x) $$ to be the expected hitting time
of reaching $$ \Omega $$ starting from state $$ x $$,
then our answer is $$ \beta(0) $$.
All we have to do is set up the first-step equations and
solve for $$ \beta(0) $$.

How can we set up these first-step equations?
Let's examine $$ \beta(3) $$ closely:

By law of iterated expectation: $$ E[X] = E[E[X \mid Y]] $$
{: .marginnote}
$$
\begin{align*}
    \beta(3) & = E[\text{steps to reach $\Omega$} \mid X_n = 3] \\
             & = E[E[\text{steps to reach $\Omega$} \mid X_n = 3 \cap X_{n+1}]] \\
             & = \sum_{x \in \mathcal{X}} \Pr(X_{n+1} = x \mid X_n = 3) E[\text{steps to reach $\Omega$} \mid X_n = 3 \cap X_{n+1} = x] \\
             & = \sum_{x \in \mathcal{X}} \Pr(X_{n+1} = x \mid X_n = 3) \big( 1 + \beta(x) \big) \\
\end{align*}
$$

If the next selection has a rating of $$0$$, $$1$$, $$2$$, or $$3$$,
then $$X_{n+1}$$ is still equal to $$3$$.
If the next selection has a rating of $$4$$, then $$X_{n+1} = 4$$.
If the next selection has a rating of $$5$$, then the sum of the ratings
$$3$$ and $$5$$ exceeds $$7.5$$, meaning $$X_{n+1} = \Omega$$.  
Continuing on,

In general, the first-step equation is
$$ \beta(i) = 1 + \sum_{j} P_{i,j} \beta(j) = 1 + E[\beta(J)] $$
where $$J$$ is the state transitioned to after $$i$$.
{: .marginnote}
$$
\begin{align*}
    \beta(3) & = \frac{4}{6} \big( 1 + \beta(3) \big) + \frac{1}{6} \big( 1 + \beta(4) \big) + \frac{1}{6} \big( 1 + \beta(\Omega) \big) \\
             & = 1 + \frac{4}{6} \beta(3) + \frac{1}{6} \beta(4) + \frac{1}{6} \beta(\Omega)
\end{align*}
$$

Setting up the rest of our first-step equations, we have

$$
\begin{align*}
    \beta(\Omega) & = 0 \\
    \beta(5) & = 1 + \frac{3}{6} \beta(5) + \frac{3}{6} \beta(\Omega) \\
    \beta(4) & = 1 + \frac{4}{6} \beta(4) + \frac{2}{6} \beta(\Omega) \\
    \beta(3) & = 1 + \frac{4}{6} \beta(3) + \frac{1}{6} \beta(4) + \frac{1}{6} \beta(\Omega) \\
    \beta(2) & = 1 + \frac{3}{6} \beta(2) + \frac{1}{6} \big(\beta(3) + \beta(4) + \beta(5)\big) \\
    \beta(1) & = 1 + \frac{2}{6} \beta(1) + \frac{1}{6} \big(\beta(2) + \beta(3) + \beta(4) + \beta(5)\big) \\
    \beta(0) & = 1 + \frac{1}{6} \big(\beta(2) + \beta(3) + \beta(4) + \beta(5)\big)
\end{align*}
$$

Solving this system of equations, we get $$ \beta(0) = \frac{31}{6} $$.

---

> If the movie ratings are instead uniformly distributed over
$$ [ 0, 5 ] $$, what is the expected number of movies
you will need to select?

As before, let's define $$ X_n $$ as the maximum rating so far
(unless the terminal state $$\Omega$$ is reached), and
$$ Y \sim \mathrm{Uniform}[0, 5] $$ as the rating of the 
next movie selected.

1. Suppose $$ X_n \in [ 0, 2.5 ) $$.
    - No matter what $$Y$$ is, their sum cannot exceed $$ 7.5 $$,
      so $$ X_{n+1} \neq \Omega $$; in fact, $$ X_{n+1} = \max(X_n, Y) $$.
2. Suppose $$ X_n \in [ 2.5, 3.75 ) $$.
    - If $$ Y \in [ 0, X_n ) $$, then $$ X_{n+1} = X_n $$.
    - If $$ Y \in [ X_n, 3.75 ) $$, then $$ X_{n+1} = Y $$.
    - If $$ Y \in [ 3.75, 7.5 - X_n ) $$, then
      their sum does not exceed $$ 7.5 $$ and $$ X_{n+1} = Y $$.
    - Otherwise, $$ Y \in [ 7.5 - X_n, 5 ] $$ and their sum exceeds $$7.5$$
      so we reach the terminal state $$ X_{n+1} = \Omega $$.
3. Suppse $$ X_n \in [ 3.75, 5 ] $$.
    - If $$ Y \in [ 0, 7.5 - X_n ) $$, then their sum does not exceed $$7.5$$
      and $$ X_{n+1} = X_n $$.
    - Otherwise, $$ Y \in [ 7.5 - X_n , 5 ] $$ and we reach the terminal state.

Using the above cases as a guide, let's define our first-step equation
$$ \beta(x) $$ as a piecewise function:

It's reasonable to assume that $$\beta$$ is a continuous function,
so $$a(2.5) = b(2.5)$$ and $$b(3.75) = c(3.75)$$.
{: .marginnote}
$$
\begin{align*}
    \beta(x) & = \begin{cases}
        a(x) , & x \in [ 0, 2.5 ) \\
        b(x) , & x \in [ 2.5, 3.75 ) \\
        c(x) , & x \in [3.75, 5] \\
        0 ,    & x = \Omega
    \end{cases}
\end{align*}
$$

Let's look at one of these functions.
What is $$b(x)$$ (when $$X_n = x \in [ 2.5, 3.75 )$$)?

$$
\begin{align*}
    b(x) & = 1 + E[\beta(X_{n+1})] \\
         & = 1 + E[E[\beta(X_{n+1}) \mid Y]] \\
         & = 1 + \int_0^5 E[\beta(X_{n+1}) \mid Y=y] f_Y(y) dy \\
         & = 1 + \int_0^x b(x) f_Y(y) dy + \int_x^{3.75} b(y) f_Y(y) dy + \int_{3.75}^{7.5-x} c(y) f_Y(y) dy + \int_{7.5-x}^5 \beta(\Omega) f_Y(y) dy \\
         & = 1 + \frac{1}{5} \big( \int_0^x b(x) dy + \int_x^{3.75} b(y) dy + \int_{3.75}^{7.5-x} c(y) dy + \int_{7.5-x}^5 \beta(\Omega) dy \big) \\
\end{align*}
$$

Repeating the above for $$a(x)$$ and $$c(x)$$
we get the following first-step equations:

$$
\begin{align*}
    \beta(\Omega) & = 0 \\
    a(x) & = 1 + \frac{1}{5} \big( \int_0^x a(x) dy + \int_x^{2.5} a(y) dy + \int_{2.5}^{3.75} b(y) dy + \int_{3.75}^5 c(y) dy \big) \\
    b(x) & = 1 + \frac{1}{5} \big( \int_0^x b(x) dy + \int_x^{3.75} b(y) dy + \int_{3.75}^{7.5-x} c(y) dy + \int_{7.5-x}^5 \beta(\Omega) dy \big) \\
    c(x) & = 1 + \frac{1}{5} \big( \int_0^{7.5-x} c(x) dy + \int_{7.5-x}^5 \beta(\Omega) dy \big)
\end{align*}
$$

Solving for $$c(x)$$ first,

$$
\begin{align*}
    c(x) & = 1 + \frac{1}{5} \big( (7.5-x) c(x) + 0 \big) \\
         & = \frac{10}{2 x - 5}
\end{align*}
$$

Next, $$b(x)$$:

$$
\begin{align*}
    b(x) & = 1 + \frac{1}{5} \big( \int_0^x b(x) dy + \int_x^{3.75} b(y) dy + \int_{3.75}^{7.5-x} c(y) dy + \int_{7.5-x}^5 \beta(\Omega) dy \big) \\
    5 b(x) & = 5 + \int_0^x b(x) dy + \int_x^{3.75} b(y) dy + \int_{3.75}^{7.5-x} c(y) dy + 0 \\
           & = 5 + x b(x) + B(3.75) - B(x) + C(7.5-x) - C(3.75) \\
    5 b'(x) & = b(x) + x b'(x) - b(x) - \frac{10}{2 (7.5-x) - 5} \\
            & = x b'(x) - \frac{10}{2 (7.5-x) - 5} \\
    b(x) & = \frac{5}{x - 5} + \text{constant}
\end{align*}
$$

$$b(x)$$ and $$c(x)$$ should have the same value
at the boundary, so $$b(3.75) = c(3.75)$$, and we can solve
for the constant and find
$$ b(x) = \frac{5}{x-5} + 8 $$.

Finally, $$a(x)$$:

$$
\begin{align*}
    a(x) & = 1 + \frac{1}{5} \big( \int_0^x a(x) dy + \int_x^{2.5} a(y) dy + \int_{2.5}^{3.75} b(y) dy + \int_{3.75}^5 c(y) dy \big) \\
    5 a(x) & = 5 + \int_0^x a(x) dy + \int_x^{2.5} a(y) dy + \int_{2.5}^{3.75} b(y) dy + \int_{3.75}^5 c(y) dy \\
           & = 5 + x a(x) + A(2.5) - A(x) + B(3.75) - B(2.5) + C(5) - C(3.75) \\
    5 a'(x) & = a(x) + x a'(x) - a(x) \\
            & = x a'(x) \\
    a(x) & = \text{constant}
\end{align*}
$$

Again, we can use the boundary and say $$a(2.5) = b(2.5)$$,
so $$a(x) = 6$$.

This leads us to our final answer, $$\beta(0) = a(0) = 6$$.

A quick Monte Carlo simulation tells us we can be reasonably confident in our
answer:

```python
import numpy as np


def simulate() -> int:
    count: int = 0
    curr: float = 0.0
    while True:
        count += 1
        draw: float = np.random.uniform(low=0.0, high=5.0)
        if draw + curr > 7.5:
            return count
        curr = max(curr, draw)


n = 10000
results = [simulate() for _ in range(n)]
print(np.mean(results))
```
```
6.0322
```
