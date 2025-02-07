# Discrete math laboratory work №1
> Researching algorithms on trees and decision tree structure.

### Kruskal's algorithm
Kruskal's algorithm finds a minimum spanning tree of a connected edge-weighted graph.

#### Implementation details
At the beggining function receives randomly generated graph.

Then we extract edges, sort them by weight which is needed for algorithm's instance and initialize
2 dictionaries mstk_v and mstk - dictionaries that contain information about vertices and edges
in minimum spanning tree and update it as algorithm is being performed.

#### Additional function for uniting groups
As we perform Kruskal's algorithm, we group vertices and edges according to their connections and the weights of the connections. But when we come across the egde, which connects two vertices that are in different groups - we need to unite those two groups into one (actually, we just add the smaller one into the bigger one). <br>
So, the  `key_1` property gets the key of group in dictionary, to which we are going to add the group marked as `key_2` in the same dictionary (basically, it applies to the both vertices dict and edges dict) <br>

#### The actual algorithm
So, as we have all the edges sorted in ascending order, we iterate through them. <br>
For each iteration we have an edge `(v, u)`. <br>
We then go through the dictionary of grouped vertices, each item of which is turned into a tuple `(group_n, [vertices])`, and check, if the `v` vertice is already in any of the groups. If it is - we pass the key of the group to the `key_0`. The same we do for the `u` vertice and `key_1` var. <br>

##### Going through conditions
- If we discover, that none of the vertices is defined by a group, we create a new one for them both - the same we do for the edge in `mstk` dict.<br>
- If this is not our case, we check whether both of the vertices are in the same group - if they are, by adding this edge to our group we would create a cycle and ruin the spanning tree - therefore we simply skip this edge. <br>
- Then we come to the third check - defining, if one of the vertices is already in group and the other one is an 'orphan'. In this case we just add the 'orphan' vertice into the group and the same for the edge we examine. <br>
- If no condition has been satisfied yet, we consider our vertices to be in two different groups - so we call the uniting function. 

<i>And that's all.<i>




<hr>

### Bellman-Ford algorithm
The Bellman-Ford algorithm is an algorithm that computes 
the shortest paths <br> from a single source vertex to all other vertices in a weighted digraph.
Implementation details
#### At the beggining function receives randomly generated graph, node to start algorithm performence from and the sign to show the distances in written form.

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
