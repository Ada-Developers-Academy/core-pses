# Instructor: Components of a Graph

## DFS Solution using Recursion - O(N + E) time, O(N) space

```py
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

## BFS Solution - O(N + E) time, O(N) space

```py
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