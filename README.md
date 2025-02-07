# Discrete math laboratory work №1
> Researching algorithms on trees and decision tree structure.

### Kruskal's algorithm
Kruskal's algorithm finds a minimum spanning tree of a connected edge-weighted graph.

#### Implementation details
At the beggining function receives randomly generated graph.

Then we extract edges, sort them by weight which is needed for algorithm's instance and initialize
2 dictionaries mstk_v and mstk - dictionaries that contain information about vertices and edges
in minimum spanning tree and update it as algorithm is being performed.

#### Starting the algorithm




<hr>

### Bellman-Ford algorithm
The Bellman-Ford algorithm is an algorithm that computes 
the shortest paths <br> from a single source vertex to all other vertices in a weighted digraph.
#### Implementation details
At the beggining function receives randomly generated graph, node to start algorithm performence from and the sign to show the distances in written form.

Then we extract edges, nodes, start node and initialize distance_dict - dictionary that contains information about distances, with node as keys and distance as values.

#### Starting the algorithm
- We initialize the distances to infinity, except for the start node - its distance is set to 0.
- Starting the main part - iterating for v-1 times, where v is a number of nodes of a graph. We iterate through our directed graph and implement a checking if the sum of a distance to start node in from node "u" in our 'table' of distances and the weight of a given edge is less than a distance to node v. If so the distance from our node v is set to such sum (previously checked that if the node distance is set to infinity it is being reset to 0 for calculation)
- As a next step we perform another additional iteration as a checking if the graph contains any negative cycles. The checking is the exact copy of the previous iterations.
- As a result we print the results in written form and in dictionary as well.
<hr>

### Decision Tree
The dataset used for this decision tree is breast cancer dataset which contains an information about whether 
the tumor is malignant or benign and 8 other features that help to make a research.
[Dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html)

<i>@Created by Iia Maharyta and Oksana Moskviak </i>
