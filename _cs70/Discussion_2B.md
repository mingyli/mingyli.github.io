---
title: Discussion 2B
topic: Graphs
---

# 1 Touring Hypercube
## Tours
- **Eulerian tour**: a tour that traverses each edge exactly once
- **Hamiltonian tour**: a tour that traverses each vertex exactly once (except for start/end vertex)
  - (It is easy to check whether a graph has an Eulerian tour, but there is no known fast algorithm to check whether a graph has a Hamiltonian tour)

## Hypercubes

A hypercube of degree $$n$$ has $$2^n$$ vertices, labeled by all $$n$$-length bit strings. It is composed of two sub-hypercubes of degree $$n-1$$, which are connected by $$2^{n-1}$$ edges.
For an $$n$$-dimensional hypercube:

- each vertex has degree $$n$$
- there are $$n 2^{n-1}$$ edges
- you can assign $$n$$-length bit string labels to the vertices such that adjacent vertices differ by exactly one bit

Because of the recursive nature of how hypercubes are constructed, proofs by induction are very powerful for hypercubes.

# 2 Trees

If a complete graph is the most connected a graph can be, a tree is the least connected a graph can be before being disconnected.
A tree on $$n$$ vertices

- is connected
- has $$n-1$$ edges
- has no cycles

Proofs by induction on trees also work well because removing leaves of a tree gives you a tree.

## Problem

> Prove that all trees must have a leaf (a vertex with degree $$1$$).

*Proof*: Suppose there were no leaves. Then every vertex would have degree at least $$2$$. From the previous discussion, we showed that if every vertex has degree at least $$2$$, then there must be a cycle. This contradicts the fact that trees acyclic.

# 3 Edge Colorings

When dealing with edge colorings, it can be helpful to think of how many colors a vertex touches, and how this relates to the vertex’s degree.

