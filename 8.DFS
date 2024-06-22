def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()  # Initialize visited set
    
    visited.add(start)  # Mark the start node as visited
    print(start, end=" ")  # Process (print) the node
    
    # Visit all adjacent nodes that have not been visited
    for neighbor in graph[start]:
        if neighbor not in visited:
            dfs(graph, neighbor, visited)

# Example usage:
if __name__ == "__main__":
    # Define a sample graph as an adjacency list
    graph = {
        'A': ['B', 'C'],
        'B': ['A', 'D', 'E'],
        'C': ['A', 'F'],
        'D': ['B'],
        'E': ['B', 'F'],
        'F': ['C', 'E']
    }
    
    print("DFS traversal starting from node A:")
    dfs(graph, 'A')
