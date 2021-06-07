# k-plex
In this work, we propose a practical SAT-based approach to enumerating all maximal
k-plexes of a graph. Our approach is based on a novel graph decomposition technique 
leading to an efficient SAT-based k-plex encoding that scales up to graphs with millions of edges.
At the core of our approach is an efficient SAT encoding which takes a graph and an integer k as input and produces a propositional 
CNF formula where its models correspond to the maximal k-plexes. 
Two additional constraints, namely the connectivity and size constraints, are also introduced to deal with the enumeration
of maximal connected k-plexes of size at least $\alpha$.
Interestingly, by setting k to 1, our encoding can be used to enumerate all maximal cliques.

---------------------------------------------------------------------------------------------

To execute the code, you simply type:

./max_kplex -min-size=$\alpha$ -k=$k$ -verb=0 graph-file

- $\alpha$: minimum size
- $k$: k-plex
- verb: 3 to print the maximal connected k-plexes, otherwise we simply set 0

 The graph file should have the following format:
  - Each line contain one edge
  - For each edge, one line containing the indices of its extremes and ends with the number 0.
  
  Example of graph file:
  
  1 2 0
  
  1 3 0
  
  For example, to count maximal connected 2-plexes bigger than 1 on the 'example' graph, you should execute the following command:
  ./max_kplex  -min-size=2 -k=2 -verb=3 example
