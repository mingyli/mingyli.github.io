---
layout: project
title: test tex
date: 2017-05-18
link: #
---

here i am testing kramdown's support for math

From AIME I 2015:

Consider all 1000-element subsets of the set \\( \\{1,2, \ldots ,2015 \\} \\). From each subset choose the least element. Find the arithmetic mean of these least elements.

*Solution*

There are \\( \binom{2015}{1000} \\) subsets of cardinality 1000. 
How many of these subsets have \\(1\\) as the least element? To construct each of these subsets, we choose 1 to be in the set, and then 999 of the remaining 2014 numbers. So there are \\( \binom{2014}{999} \\) subsets with 1 as the least element.

What about the number of subsets that have \\( i \\) as the least element? Like before, we choose \\( i \\) to be in each subset. Since \\( i \\) must be the least element, the remaining elements must be from the \\( 2015 - i \\) elements greater than \\( i \\). Then there are \\( \binom{2015-i}{999} \\) such subsets.

To find the arithmetic mean of the least elements, we sum the least elements and divide by the number of subsets of size 1000. The sum of the least elements is

$$
\begin{align*}
S &= 1 \cdot \binom{2014}{999} + 2 \cdot \binom{2013}{999} + \cdots + 1016 \cdot \binom{999}{999} \\
  &= \binom{999}{999} + \cdots + \binom{2012}{999} + \binom{2013}{999} + \binom{2014}{999} \\
  & \quad + \binom{999}{999} + \cdots + \binom{2012}{999} + \binom{2013}{999} \\
  & \quad \vdots \\
  & \quad + \binom{999}{999} \\
  &= \binom{2015}{1000} + \binom{2014}{1000} + \cdots + \binom{1000}{1000} \\
  &= \binom{2016}{1001}
\end{align*}
$$

Here we used the [Hockey Stick Identity](https://en.wikipedia.org/wiki/Hockey-stick_identity).

Now that we have the sum, we solve for the arithmetic mean.

$$ \frac{\binom{2016}{1001}}{\binom{2015}{1000}} = \frac{2016}{1001} $$

<!--Let \\( f(x) \\) be a third-degree polynomial with real coefficients satisfying

$$ 
|f(1)|=|f(2)|=|f(3)|=|f(5)|=|f(6)|=|f(7)|=12 
$$

Find \\( \lvert f(0) \rvert \\).

*Solution*

Note that it does not matter if we find \\( -f(x) \\) or \\( f(x) \\) because the answer will be the same. 
Since \\( f(x) \\) is cubic, \\( f(x) = c \\) for some value \\( c \\) at at most three values of \\( x \\). 
So we can choose \\( f(1) = 12 \\). -->