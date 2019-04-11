---
title: Discussion 2A
topic: Graphs
---

# Discussion 2A

# 1. Graph Basics
- **graph**: $$G = (V, E)$$ consists of vertices $$V$$ connected by edges $$E$$
  - **directed**: edges have directions
  - **connected**: there is a path between any two vertices
- **adjacent**/**neighboring**: two vertices with an edge between them
- **degree**: number of edges on a vertex in an undirected graph
  - **indegree**/**outdegree**: number of edges going into and out of a vertex, respectively, in a directed graph
- **path**: sequence of edges connected by endpoints
  - in this class paths are *simple paths*, which means vertices are not reused
- **cycle**: path that begins and ends on same vertex
- **walk**: sequence of edges connected by endpoints, which can be repeated
- **tour**: walk that begins and ends on same vertex

# 2. Planarity
- **planar**: a graph that can lie on a plane without edges crossing
- **complete graph**: $$K_n$$ graph on $$n$$ vertices where an edge exists between every pair
  - $$K_1$$, $$K_2$$, $$K_3$$, and $$K_4$$ are planar
  - $$K_5$$ is not planar
- **complete bipartite graph**: $$K_{m,n}$$ is a bipartite graph where an edge exists between every pair of vertices on different sides
  - $$K_{3,3}$$ is not planar (it can be drawn on a donut without edges crossing)
- A graph containing $$K_5$$ or $$K_{3,3}$$ is not planar

# 3. Bipartite Graph
## Proof Structure
1. \\( \text{bipartite} \Rightarrow \text{no tours of odd length} \\)
    - prove that if there is a tour, then it must have even length
2. \\( \text{no tours of odd length} \Rightarrow \text{bipartite} \\)
    - prove that you can partition the vertices into two sets $$L$$ and $$R$$ such that within in each set, there are no edges

