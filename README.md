# Discrete math laboratory work №1
> Researching algorithms on trees and decision tree structure.

## Kruskal's algorithm
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






## Bellman-Ford algorithm
### Implementation details
At the beginning, the function receives a randomly generated graph, a node to start algorithm performance from, and a sign to show the distances in written form.

Then we extract edges, nodes, start node and initialize <b>distance_dict</b> - a dictionary that contains information
about distances, with node as keys and distance as values.

### Starting the algorithm
- We initialize the distances to infinity, except for the start node, whose distance is set to 0.
- Starting the main part - iterating for `v-1` times, where `v` is the number of nodes of a graph. We iterate through our directed graph and implement a checking if the sum of a distance to start node in from node `u` in our 'table' of distances and the weight of a given edge is less than a distance to node `v`. If so the distance from our node `v` is set to such sum (previously checked that if the node distance is set to infinity it is being reset to 0 for calculation)
- As a next step we perform another additional iteration as a check if the graph contains any negative cycles. If the distances were changed after this iteration - there's a negative cycle. The check is the exact copy of the previous iterations.
- As a result, we print the results in written form and a dictionary as well.

## Decision Tree Classifier
The dataset used for this decision tree is breast cancer dataset which contains an information about whether 
the tumor is malignant or benign and 8 other features that help to make a research.
[Dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html)

### Description of an algorithm
- First of all, we initialize the class for a node of our decision tree <br>
and the function that checks if the node is a leaf.
- Then we initialize the main class for the decision tree, which controls all of the algorithm.
- We initialize the `fit` function which controls all of the processes in our algorithm
- `build_tree` - is the core of an algorithm, a recursive function that builds the tree according to such aspects as the calculation of a best feature and threshold for it to divide the tree into left and right subtrees. It continues to the point where we reach the given maximum depth or the number of samples in a node is smaller than needed or the number of labels is equal to one.
- In the previous function we use helping functions such as `find_best_split` and `split` function.
- `find_best_split` - finds the best feature and threshold for it if it gives the best information gain. Information gain is calculated in `calculate_info_gain` using the gini index of a parent and children (left and right values). <br> 
The Gini index is calculated in the `gini` function by standard formula and numpy features.
- Now back to split function which splits the data into left and right subtrees according to the threshold value.
- `traverse_tree` and `predict` functions are used to store the information about predictions in the tree
- Final `evaluate` function calculates the accuracy of a model for testing data from sckit-learn.

<i>@Created by Iia Maharyta and Oksana Moskviak </i>
