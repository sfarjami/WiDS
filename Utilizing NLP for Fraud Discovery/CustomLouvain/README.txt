This package implements the Louvain clustering algorithm on graphs with modifications to the modularity function.
The modifications to the modularity function enables the algorithm detect smaller communities in the large graph. 
Changes to the modularity function impacts the way the graph optimizes convergence. It is recommended that users test
this algorithm and compare clusters generated to other clustering algorithms, such as the original Louvain package. 

To use this algorithm, simply download the code from this repo and place your project folder. 

To run the package in Python, use the following import statement: 
>>> from CustomLouvain import louvain_modified

To run the algorithm in NetworkX on G_un, an undirected graph:
>>> my_clusters = louvain_modified.best_partition(G_un)

This algorithm also works with weighted graphs. To run the algorithm on a weighted, undirected graph using NetworkX: 
>>> my_clusters_weighted = louvain_modified.best_partition(G_un, weight='weight')

Please note: 
This program only runs on undirected graphs. If you are working with a directed graph, you should first convert your graph to an undirected graph.
If your graph has weighted edges (and you plan to use this when you run CustomLouvain, we recommend that you avoid using networx.DiGraph.to_undirected() 
because this algorithm deletes bi-directional edges. One work-around we discovered is to create a sum of bi-directional edges in a pandas dataframe.