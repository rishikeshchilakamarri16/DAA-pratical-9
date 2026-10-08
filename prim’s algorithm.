import sys

def prim(graph, n):
    selected = [False] * n
    key = [sys.maxsize] * n
    parent = [-1] * n

    key[0] = 0

    for _ in range(n):
        # Find the vertex with minimum key value
        min_key = sys.maxsize
        u = -1

        for v in range(n):
            if not selected[v] and key[v] < min_key:
                min_key = key[v]
                u = v

        selected[u] = True

        # Update adjacent vertices
        for v in range(n):
            if graph[u][v] != 0 and not selected[v]:
                if graph[u][v] < key[v]:
                    key[v] = graph[u][v]
                    parent[v] = u

    # Print MST
    print("Edge \tWeight")
    total_weight = 0

    for i in range(1, n):
        print(parent[i], "-", i, "\t", graph[i][parent[i]])
        total_weight += graph[i][parent[i]]

    print("Total weight:", total_weight)


# Example graph using adjacency matrix
graph = [
    [0, 2, 0, 6, 0],
    [2, 0, 3, 8, 5],
    [0, 3, 0, 0, 7],
    [6, 8, 0, 0, 9],
    [0, 5, 7, 9, 0]
]

n = len(graph)

prim(graph, n)
