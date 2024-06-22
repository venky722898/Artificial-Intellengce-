from collections import deque

def bfs(graph, start):
    visited = set()         # To keep track of visited nodes
    queue = deque([start])  # Initialize the queue with the start node
    
    while queue:
        node = queue.popleft()  # Remove and return an element from the left side of the deque
        if node not in visited:
            print(node, end=" ")  # Process the node (here, we print it)
            visited.add(node)     # Mark the node as visited
            
            # Add all unvisited neighbors to the queue
            for neighbor in graph[node]:
                if neighbor not in visited:
                    queue.append(neighbor)

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
    
    print("BFS traversal starting from node A:")
    bfs(graph, 'A')
