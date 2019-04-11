---
title: Discussion 3B
topic: Bijections and Chinese Remainder Theorem
dropbox: https://paper.dropbox.com/doc/Discussion-3B--Aa7SrS8IoXBwTKc9CudbJh9LAQ-QAvV9QCoezaVnS62hPOg6
---

# Discussion 3B

# Bijections

Consider two sets $$A$$ and $$B$$, and a function $$f : A \mapsto B$$ that maps elements from $$A$$ to the elements of $$B$$.

- $$f$$ is **injective** if each element in $$B$$ has at most one element in $$A$$ that maps to it
- $$f$$ is **surjective** if each element in $$B$$ has at least one element in $$A$$ that maps to it
- $$f$$ is **bijective** if it is both injective and surjective
  - $$f$$ is bijective if and only if it has an inverse $$f^{-1}$$

# Chinese Remainder Theorem

## Goal

Given a list of congruences $$x \equiv a_1 \mod m_1$$, $$x \equiv a_2 \mod m_2$$, $$\cdots$$, $$x \equiv a_n \mod m_n$$, find an $$x$$ that satisfies all congruences.

## Theorem

Let $$N = m_1 m_2 \cdots m_n$$. If all the $$m_i$$ are relatively prime ($$\gcd(m_i, m_j) = 1$$) then there is exactly one value of $$x$$ in the set $$\{ 0, 1, \cdots, N-1 \}$$ that satisfies all the congruences.

## Finding $$x$$

For $$x \equiv a_1 \mod m_1$$ and $$x \equiv a_2 \mod m_2$$, we want to find a number $$k_1$$ that is a multiple of $$m_2$$ and $$k_1 \equiv 1 \mod m_1$$, and similarly a number $$k_2$$ that is a multiple of $$m_1$$ and $$k_2 \equiv 1 \mod m_2$$. Then $$x = a_1 k_1 + a_2 k_2$$ is a solution because $$x \equiv a_1 k_1 + 0 \equiv a_1 \mod m_1$$ and $$x \equiv 0 + a_2 k_2 \equiv a_2 \mod m_2$$.

