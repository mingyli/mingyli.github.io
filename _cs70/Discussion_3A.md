---
layout: note
title: Discussion 3A
topic: Build-up error and modular arithmetic
dropbox: https://paper.dropbox.com/doc/Discussion-3A--Aa5aECmHh5COFiiyVx0YqWx4AQ-eQ875X6IWlRQwtWYO7rjT
---

# Discussion 3A

# Build-up Error in Graphs

> Prove that if every vertex in a graph has positive degree, then the graph is connected.

*Proof*: Induction on the number of vertices $$n$$

1. *Base case*: If we have $$n=1$$ vertex then the proposition is vacuously true. If we have $$n=2$$ vertices with no edge then the proposition is vacuously true; with one edge between the two vertices, each edge has degree $$1$$ (positive) and the graph is connected.
2. *Inductive hypothesis*: Assume if every vertex has positive degree in a graph on $$k$$ vertices, then the graph is connected.
3. *Inductive step*: Begin with a graph on $$k$$ vertices where every vertex has positive degree. The inductive hypothesis says this graph is connected. Then adding a new vertex with positive degree gives us a graph with $$k+1$$ vertices, all with positive degree. Since the new vertex has positive degree, it has some edge connecting it to another vertex in the original graph, meaning the graph with $$k+1$$ vertices with positive degree is connected. 

Since we proved a graph with $$k$$ vertices with positive degree that is connected can create a graph with $$k+1$$ vertices with positive degree that is connected, the proof is complete.

----------

It turns out that this is actually a false statement, which can be disproved with the counterexample consisting of two disjoint edges on four vertices.
The issue is that in showing $$P(k) \Rightarrow P(k+1)$$ in the inductive step, we incorrectly assume that the proof applies for every graph on $$k+1$$ vertices with positive degree. We only show that it’s true for *some* graphs on $$k+1$$ vertices: only the ones that can be built up from graphs on $$k$$ vertices that are already connected. 
To avoid build-up error in proofs, begin with $$k+1$$ vertices/edges and remove one, so you can use the inductive hypothesis for $$k$$ vertices/edges.

# Modular Arithmetic
If $$a \equiv b \mod m$$ (pronounced “$$a$$ is congruent to $$b$$ modulo $$m$$”) then $$a = b + m k$$ for some integer $$k$$.
$$a \mod m$$ is congruent to one integer in the set $$\{0, 1, \cdots, m-1\}$$.

If $$a \equiv c \mod m$$ and $$b \equiv d \mod m$$ then $$a+b \equiv c+d \mod m$$ and $$a b \equiv c d \mod m$$.
Subsequently, $$a^k \equiv c^k \mod m$$.

$$a$$ and $$b$$ are multiplicative inverses modulo $$m$$ when $$a b \equiv 1 \mod m$$.
$$a$$ has a multiplicative inverse if and only if $$\gcd(a, m) = 1$$.