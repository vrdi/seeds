# seeds
Exploring new methods for generating initial partitions for gerrychain.

Most of the methods that have been explored so far to create initial partitions (including the currently implemented method recursive_tree_part ) in the context of running chains with gerrychain for redistricting present the following characteristics:
- they are tree-based methods (using spanning trees on the dual graph)
- districts are carved out of the graph one by one. More precisely, a constraint - typically population deviation from ideal balanced population between districts - is set, and districts will be built one after the other, trying to satisfy this bound. 

The following questions arise when using a method for generating initial partitions: 
- Can the population constraint be satisfied ? How can we ensure it is satisfied ? 
- Does this method allow to explore the whole space of possible partitions or are we generating partitions that look the same ? 
- What can we say about the compactness of the initial partitions ? 
- What is the computation time ? 

A first exploration into these tree methods is summarized in the [Trees.pdf](seeds/Trees.pdf) file. 
A notable result is the proof that no spanning tree method is subset-separable (with a counter example on an 8 nodes graph). 

Two methods were explored in this project : 
- a floodfill method which does NOT rely on trees but builds districts one by one
- a "divide and conquer" method, which while using spanning trees, iteratively bipartitions the graph in equal parts until the number of districts to build is reached. 





