# Implement Components of a Graph

## Problem

Given an undirected graph represented by an adjacency dictionary, `g`, return a list of lists containing all of the subgraphs in the graph. Each element in the outer list will represent a subgraph in the graph. Each element in the inner lists will contain all of the nodes in a subgraph. Please note the items in the inner lists must be sorted from least to greatest.

The goal is to return a list of lists containing all of the subgraphs in graph `g`. 

**Example 1:**

![example graph 1](./images/graph1.png)

```
Input: 

g = {
    1: [2],
    2: [1, 3],
    3: [2],
    4: [5],
    5: [4]
}

Output: [[1, 2, 3], [4,5]]
Explanation: The nodes 1, 2, & 3 are all connected together, and thus comprise a list in the output. Similarly, the nodes 4 & 5 are connected to each other, and comprise another list in the output.
```

**Example 2:**

![example graph 2](./images/graph2.png)

```
Input:

g = {
    "A": ["B", "C"],
    "B": ["A", "C"],
    "C": ["A", "B"],
    "D": ["E"],
    "E": ["D"],
    "F": []
}

Output: [["A", "B", "C"], ["D", "E"], ["F"]]
Explanation: The nodes A, B, and C are all connected, so will be an item in the list. Nodes D and E are connected, so will be another item in the resulting list. Finally, node F is not connected to any other node, so it is the only item in the final list.
```

**Example 3:**

![example graph 3](./images/graph3.png)

```
Input: 

g = {
    "B": []
}

Output: [["B"]]
Explanation: Node B is the only node in the graph, so the function will return a list containing one list, which will contain one item, node B.
```

Adapted from:  [GeeksForGeeks](https://www.geeksforgeeks.org/connected-components-in-an-undirected-graph/)

### !challenge

* type: code-snippet
* language: python3.6
* id: 9e3f523a-4088-4595-a1a3-5a204fffbb6d
* title: Graph Components Coding Challenge
* points: 3
* topics: python, graphs, traversals

##### !question

Write a solution to the Graph Components function below.

##### !end-question

##### !placeholder

```py
def components(g):
    pass

```

##### !end-placeholder

##### !tests

```py
import unittest
from main import components

class TestPython1(unittest.TestCase):
    def test_components_example_one(self):
        # Arrange
        g = {
            1: [2],
            2: [1, 3],
            3: [2],
            4: [5],
            5: [4]
        }

        # Act
        answer = components(g)
        answer.sort()

        # Assert
        self.assertEqual(answer, sorted([[1,2,3],[4,5]]))

    def test_components_example_two(self):
        # Arrange
        g = {
            "A": ["B", "C"],
            "B": ["A", "C"],
            "C": ["A", "B"],
            "D": ["E"],
            "E": ["D"],
            "F": []
        }

        # Act
        answer = components(g)
        answer.sort()

        # Assert
        self.assertEqual(answer, sorted([["A", "B", "C"], ["D", "E"], ["F"]]))

    def test_components_example_three(self):
        # Arrange
        g = {
            "B": []
        }

        # Act
        answer = components(g)
        answer.sort()

        # Assert
        self.assertEqual(answer, [["B"]])
        
    def test_components_empty_graph(self):
        # Arrange
        g = {}

        # Act
        answer = components(g)

        # Assert
        self.assertEqual(answer, [])
```

##### !end-tests

##### !explanation

Our DFS solution:

```python

# a function to perform a depth first traversal on the subgraph
def dfs(temp, visited, graph, node):
    # if the node has not been previously visited
    if node not in visited:
        # add the node to the visited list
        visited.append(node)
        # add the node to the temp visited list
        # the temp visited list keeps track of the nodes in the current subgraph
        temp.append(node)
        # visit each neighbor connected to the current node
        for neighbor in graph[node]:
            # perform a depth first traversal on the neighboring node
            dfs(temp, visited, graph, neighbor)

def components(g):
    # if the graph is empty, return an empty list, incidating there are no subgraphs in the graph
    if len(g) == 0:
        return []

    # intialize a list to keep track of the subgraphs encountered in the graph
    result = []
    # initialize a visited list to keep track of all of the nodes previously visited
    visited = []

    # for each node in the graph
    for node in list(g.keys()):
        # if the node has not yet been visited
        if node not in visited:
            # initialize a temporary list to keep track of the nodes in this subgraph
            temp = []
            # perform a depth first traversal on this node and its neighbors
            dfs(temp, visited, g, node)
            # sort the resulting temporary list of this subgraph
            temp.sort()
            # append the temporary list to the resulting list of subgraphs
            result.append(temp)
    
    # return the list of subgraphs
    return result
```

Our BFS solution:

```python
# a function to perform a breadth first traversal on the subgraph
def bfs(temp, visited, graph, node):
    from collections import deque

    # initialize a queue to keep track of the nodes we need to visit
    queue = deque([node])
    # append the current node to the list of visited nodes
    visited.append(node)
    # append the current node to the list of temporarily visited nodes for this subgraph
    temp.append(node)

    # while the queue is not empty
    while queue:
        # pop off the first node in the queue
        current = queue.popleft()

        # visit each neighbor connected to the current node
        for neighbor in graph[current]:
            # if the neighbor has not yet been visited
            if neighbor not in visited:
                # add the neighbor to the list of visited nodes
                visited.append(neighbor)
                # add the neighbor to the temp list for this subgraph
                temp.append(neighbor)
                # add the neighbor to the queue so it can be visited in this traversal
                queue.append(neighbor)

def components(g):
    # if the graph is empty, return an empty list, incidating there are no subgraphs in the graph
    if len(g) == 0:
        return []

    # intialize a list to keep track of the subgraphs encountered in the graph
    result = []
    # initialize a visited list to keep track of all of the nodes previously visited
    visited = []

    # for each node in the graph
    for node in list(g.keys()):
        # if the node has not yet been visited
        if node not in visited:
            # initialize a temporary list to keep track of the nodes in this subgraph
            temp = []
            # perform a breadth first traversal on this node and its neighbors
            bfs(temp, visited, g, node)
            # sort the resulting temporary list of this subgraph
            temp.sort()
            # append the temporary list to the resulting list of subgraphs
            result.append(temp)
    
    # return the list of subgraphs
    return result
```

##### !end-explanation

### !end-challenge

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->

### !challenge

* type: paragraph
* id: a4a59483-3ca1-483d-9f39-4d35217d4f1c
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O, python

##### !question

What is the time complexity of your solution? Explain. Define your variable(s).

##### !end-question

##### !placeholder

Time Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->

### !challenge

* type: paragraph
* id: 3aaf097c-fd40-4464-9c18-7b2b18af24e6
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O, python

##### !question

What is the space complexity of your answer? Explain. Define your variable(s).

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.
