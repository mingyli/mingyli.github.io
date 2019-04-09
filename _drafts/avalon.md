---
layout: note
title: Discrete Random Variables through Avalon
date: 2018-01-04
---


We're playing a game of Avalon with five people, so there are two evil players and three good players.
This round, we're randomly selecting two people to go on a mission.

#### Random Variables

**definition**: a mapping from event outcomes to numbers

Let $$X$$ be a random variable denoting the number of evil people on this mission.
The set of possible outcomes of the mission of two is $$\{GG, GE, EG, EE\}$$, and $$X$$ maps each of these outcomes to the number of evil people on the mission.

We can then define the probability distribution of $$X$$ to be the probability that the value of $$X$$ equals some $$x$$ for all values in the outcome space of $$X$$. 
So in this example, $$\Pr(X = 2) = \Pr(EE) = \frac{1}{10}$$.
The entire distribution is given by

$$
\begin{align*}
    \Pr(X = 0) &= \Pr(GG) = \frac{3}{10} \\
    \Pr(X = 1) &= \Pr(GE) + \Pr(EG) = \frac{3}{5} \\
    \Pr(X = 2) &= \Pr(EE) = \frac{1}{10} \\
    f(x) = \Pr(X = x) &= \begin{cases}
        \frac{3}{10} & \quad X = 0 \\
        \frac{3}{5} & \quad X = 1 \\
        \frac{1}{10} & \quad X = 2
    \end{cases}
\end{align*}
$$


For discrete random variables, the function $$f(x) = \Pr(X = x)$$ is known as the probability mass function.
All probability distributions have the property that the sum of the probabilities over all values of $$x$$ equals 1  $$(\sum\limits_{x} f(x) = 1)$$, which we can see is true for this Avalon example.
Another property is that for all $$x$$, $$0 \leq f(x) \leq 1$$.

#### Expected Value

**definition**: $$E[X] = \sum\limits_x x \Pr(X = x)$$

The expected number of evil people on the mission is

$$
\begin{align*}
    E[X] &= 0 \cdot \Pr(X = 0) + 1 \cdot \Pr(X = 1) + 2 \cdot \Pr(X = 2) \\
         &= 0 \cdot \frac{3}{10} + 1 \cdot \frac{3}{5} + 2 \cdot \frac{1}{10} = \frac{4}{5}
\end{align*}
$$

One thing we notice immediately about the expected value is that it isn't even a possible value for the number of evil people! 
The intuitive interpretation of the expected value is that over multiple trials of the mission selection, the average number of evil people will tend towards $$\frac{4}{5}$$. 
This makes sense in this example, as we would estimate around one evil person since $$X = 1$$ is the most likely outcome, though it is not always the case that the expected value is approximately the same as an outcome (think of a fair coin flip).

#### Linearity of Expectation

**definition**: $$E[\alpha X + Y] = \alpha E[X] + E[Y]$$ 

If we let $$X_1$$ be a random variable denoting whether the first person on the mission is evil, and similarly for $$X_2$$, then we have $$X = X_1 + X_2$$. 
Using linearity of expectation, we have $$E[X] = E[X_1] + E[X_2]$$. 
Let's see if we can verify our previous value using linearity of expectation.

$$
\begin{align*}
    E[X] &= E[X_1] + E[X_2] \\
         &= 0 \cdot \Pr(X_1 = 0) + 1 \cdot \Pr(X_1 = 1) + 
            0 \cdot \Pr(X_2 = 0) + 1 \cdot \Pr(X_2 = 1) \\
         &= \frac{2}{5} + \frac{2}{5} = \frac{4}{5}
\end{align*}
$$

We see that linearity of expectation indeed holds!
In fact, in many problems it may be much easier to calculate an expected value using linearity of expectation.
