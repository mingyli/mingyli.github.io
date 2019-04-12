---
title: Minimum Spanning Trees
date: 2019-02-17
---

# {{ page.title }}

Recall that trees are
connected and acyclic, meaning there exists exactly
one path between any two vertices.
{: .marginnote}

For a graph $$ G = (V, E) $$, a **spanning tree** is a tree
on all vertices in $$ V $$.
A **minimum spanning tree** is a spanning tree with
the least total weight, out of all spanning trees for a graph.

# Properties

The proof for this relies on the fact that
adding an edge to a tree creates a cycle.
{: .marginnote}

> Cut Property
: For any cut of $$ G $$, each edge of minimum weight
in the cut must be part of some MST.

A result of this is that
if there is only one edge of minimum weight
in the cut then it is in every MST.

> Cycle Property
: For every cycle, an edge with the greatest weight
of all edges in the cycle is not part of any MST.

# Algorithms

Here are two algorithms that produce
a minimum spanning tree for a given graph.

## Prim's Algorithm

1. Select an arbitrary vertex $$ v_0 $$
2. Initialize a tree $$ T $$ to be just $$ v_0 $$
3. While $$ T $$ does not span $$ G $$
    - Find the vertex $$ v $$ not in $$ T $$ that is closest to $$ T $$ 
      (connected by some edge $$ e $$)
    - Add $$ v $$ and $$ e $$ to $$ T $$

## Kruskal's Algorithm

1. Initialize tree $$ T = \{ \} $$
2. For each edge $$ e $$, in ascending order by weight
    - If adding $$ e $$ to $$ T $$ does not create a cycle, 
      add $$ e $$ and its vertices to $$ T $$

# Resistance to Transformations

Let $$ f : \mathbb{R} \to \mathbb{R} $$, and let
$$ F(G) $$ be the graph $$ G $$ with each edge weight
$$ w $$ replaced with $$ f(w) $$.

> **Theorem**
: If $$ f $$ is an increasing function, then a MST of $$ G $$
is also a MST of $$ F(G) $$.

> *Proof*:
Since $$ f $$ is increasing, if $$ x < y $$ then $$ f(x) < f(y) $$.
This means the relative ordering of edge weights
$$ G $$ is preserved.
Appealing to the correctness of Prim's or Kruskal's algorithms
means the edges selected in $$ F(G) $$ are the same as
those selected in $$ G $$ during the execution of these algorithms.

A similar result holds for maximum spanning trees.
However, the result does not necessarily hold for any spanning tree.
Consider a function $$ f(x) = 2^x $$ and a spanning tree $$ T_1 $$ of $$ G $$
consisting of edge weights $$ (1, 1, 5) $$
and another spanning tree $$ T_2 $$ consisting of weights
$$ (3, 3, 3) $$.
Then $$ T_1 $$ has a total weight of $$ 7 $$, which is less than
than that of $$ T_2 $$, which as a total weight of $$ 9 $$.
However, the spanning tree $$ F(T_1) $$ has weights
$$ (2, 2, 32) $$ for a total weight of $$ 36 $$,
while $$ F(T_2) $$ has weights
$$ (8, 8, 8) $$ for a total weight of $$ 24 $$.

This means if you were to take all the spanning trees
of $$ G $$ and place them in order by total weight,
transforming $$ G $$ into $$ F(G) $$ does not
shift the spanning trees at the ends of this list,
but may reorder those in the middle.

# Applications

The mutual information $$ I(X ; Y) $$ between
two random variables $$ X $$ and $$ Y $$
is a measure of the amount of information (often in bits)
gained about $$ X $$ after observing $$ Y $$.
Mutual information is symmetric so $$ I(X ; Y) = I(Y ; X) $$.
{: .marginnote}

One application of MSTs is in constructing Bayesian networks.
We can model random variables as vertices
and mutual information between random variables as edges.
We can get a tree with that maximizes the total mutual information
by applying Prim's algorithm or Kruskal's algorithm.
This is known as the
[Chow-Liu algorithm](https://en.wikipedia.org/wiki/Chow%E2%80%93Liu_tree)
and produces
the tree-structured network that best approximates
the true joint distribution of the random variables.
