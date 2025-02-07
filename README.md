# Discrete math laboratory work №1
> Researching algorithms on trees and decision tree structure.

## Kruskal's algorithm
Kruskal's algorithm finds a minimum spanning tree of a connected edge-weighted graph.

#### Implementation details
At the beggining function receives randomly generated graph.

Then we extract edges, sort them by weight which is needed for algorithm's instance and initialize
2 dictionaries mstk_v and mstk - dictionaries that contain information about vertices and edges
in minimum spanning tree and update it as algorithm is being performed.

#### Starting the algorithm






## Bellman-Ford algorithm
### Implementation details
At the beginning, the function receives a randomly generated graph, a node to start algorithm performance from, and a sign to show the distances in written form.

Then we extract edges, nodes, start node and initialize <b>distance_dict</b> - a dictionary that contains information
about distances, with node as keys and distance as values.

### Starting the algorithm
- We initialize the distances to infinity, except for the start node, whose distance is set to 0.
- Starting the main part - iterating for v-1 times, where v is the number of nodes of a graph. We iterate through our directed graph and implement a checking if the sum of a distance to start node in from node "u" in our 'table' of distances and the weight of a given edge is less than a distance to node v. If so the distance from our node v is set to such sum (previously checked that if the node distance is set to infinity it is being reset to 0 for calculation)
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
- We initialize the fit function which controls all of the processes in our algorithm
- build_tree - is the core of an algorithm, a recursive function that builds the tree according to such aspects as the calculation of a best feature and threshold for it to divide the tree into left and right subtrees. It continues to the point where we reach the given maximum depth or the number of samples in a node is smaller than needed or the number of labels is equal to one.
- In the previous function we use helping functions such as find_best_split and split function.
- find_best_split - finds the best feature and threshold for it if it gives the best information gain. Information gain is calculated in calculate_info_gain using the gini index of a parent and children (left and right values). <br> 
The Gini index is calculated in the gini function by standard formula and numpy features.
- Now back to split function which splits the data into left and right subtrees according to the threshold value.
- traverse_tree and predict functions are used to store the information about predictions in the tree
- Final evaluate function calculates the accuracy of a model for testing data from sckit-learn.

<i>@Created by Iia Maharyta and Oksana Moskviak </i>
