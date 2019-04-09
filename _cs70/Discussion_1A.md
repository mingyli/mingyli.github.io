---
layout: note
title: Discussion 1A
topic: Induction
--- 

# Discussion 1A

# Induction

> Prove that for all $$n \in \mathbb{N}$$, $$P(n)$$ holds.

## Weak induction steps:
1. **Base case:** Prove that $$P(0)$$ holds
2. **Inductive hypothesis**: Assume that $$P(k)$$ holds for some value of $$k$$
3. **Inductive step**: Show that $$P(k+1)$$ holds under the inductive hypothesis

## Strong induction steps:
1. **Base case**: Prove that $$P(0)$$ holds
2. **Inductive hypothesis**: Assume that $$P(n)$$ holds for all values of $$n$$ between $$0$$ and $$k$$
3. **Inductive step**: Show that $$P(k+1)$$ holds under the inductive hypothesis

## Applications
- Divide and conquer/recursion problems
  - Binary search, sorting
- Graphs
  - Trees

minor typo on 1b: $$1^2 + 2^2 + 3^2 + \cdots$$

