# Graphs

## Representation:
* objects/pointers = OO implementations -> vertex attributes
* adj. list = **sparse** -> memory `O(V+E)`, time `O(1)`/`O(V)`
* adj. matrix = **dense** -> memory `O(V**2)`, time `O(1)`

## Bidirectional Search:
* BFS at source and destination = `O(k**(d/2))`

## BFS & DFS:
* shortest paths and finishing times, respectively
* **finishing time**: finished iterating through all neighbors -> black
* to get time complexity, think in aggregate

## Topological Sort:
* goal: linear ordering of dag
* **intuition**: we want to organize dag so the neighbors of each node
come after the node itself -> **finishing times**:
  1. compute finishing times
  2. return nodes in descending order of finishing times

## SCCs:
* a single strongly connected component: maximal subset of vertices such
that for every pair of vertices (u, v), in the subset, we have both u -> v
and v -> u i.e. **all vertices in the subset are reachable from each other**:
  1. call `dfs(g.transpose)` but consider vertices in topologically sorted
 order
  2. each df forest = 1 scc

## SSSPs:
* **SSSP vs distance** -> BFS + weights
* neg w cycs = sp is ill-defined -> can be detected
* pos w cycs = will not be part of sp
* **relaxtion** -> check/update/relax **sp estimate** & **predecessor**
* **bellman-ford**:
  * **general**
  * make `v-1` relaxation passes, over all edges -> each pass finds
  shortest path with at most `i` edges
 * check if graph is completely relaxed
* **dag**:
  * **best order is known**
  * iterate through vertices in topo. sorted order and relax neighbors
* **dijkstra**:
  * **positive weights only([cant add constant][1])**:
  * pq
  * greedily pick vertex with min sp estimate, relax neighbors, and
  repeat until all vertices have been seen
  * base complexity -> pq + sparsity complexity
  * **TODO**: intuition behind sparse i.e. E in the set of `o(V**2/lgV)`?



[1]: https://cs.stackexchange.com/a/52082/79876
