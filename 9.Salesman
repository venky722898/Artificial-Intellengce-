import itertools
import sys

def calculate_distance(path, distances):
    total_distance = 0
    num_cities = len(path)
    for i in range(num_cities - 1):
        total_distance += distances[path[i]][path[i + 1]]
    total_distance += distances[path[-1]][path[0]]  # Return to the starting city
    return total_distance

def tsp_brute_force(distances):
    num_cities = len(distances)
    min_distance = sys.maxsize
    best_path = None
    
    # Generate all permutations of city indices
    all_permutations = itertools.permutations(range(1, num_cities))
    
    for permutation in all_permutations:
        path = [0] + list(permutation)  # Start from city 0
        current_distance = calculate_distance(path, distances)
        
        if current_distance < min_distance:
            min_distance = current_distance
            best_path = path
    
    return best_path, min_distance

# Example usage:
if __name__ == "__main__":
    # Example distances between cities (0-indexed)
    distances = [
        [0, 10, 15, 20],
        [10, 0, 35, 25],
        [15, 35, 0, 30],
        [20, 25, 30, 0]
    ]
    
    # Solve the TSP using brute-force
    best_path, min_distance = tsp_brute_force(distances)
    
    print(f"Minimum distance: {min_distance}")
    print(f"Optimal path: {best_path}")
