from collections import deque

# Directions for moving in the grid (up, down, left, right)
DIRECTIONS = [(-1, 0), (1, 0), (0, -1), (0, 1)]

def is_valid_move(grid, x, y, visited):
    rows, cols = len(grid), len(grid[0])
    return 0 <= x < rows and 0 <= y < cols and grid[x][y] != '#' and not visited[x][y]

def bfs_clean(grid):
    rows, cols = len(grid), len(grid[0])
    visited = [[False for _ in range(cols)] for _ in range(rows)]
    queue = deque()
    
    # Find initial position of the cleaner
    for i in range(rows):
        for j in range(cols):
            if grid[i][j] == 'C':
                start = (i, j)
                queue.append((start, 0))  # (position, steps)
                visited[i][j] = True
                break
    
    total_steps = 0
    dirt_count = sum(row.count('D') for row in grid)

    while queue:
        (x, y), steps = queue.popleft()
        
        # If current cell is dirty, clean it
        if grid[x][y] == 'D':
            grid[x][y] = 'C'  # Clean the dirt
            total_steps += steps
            steps = 0
            dirt_count -= 1
            queue = deque()  # Reset the queue to start BFS from the current clean cell
            visited = [[False for _ in range(cols)] for _ in range(rows)]
            visited[x][y] = True
        
        # If all dirt is cleaned, return the total steps taken
        if dirt_count == 0:
            return total_steps
        
        # Explore neighbors
        for dx, dy in DIRECTIONS:
            nx, ny = x + dx, y + dy
            if is_valid_move(grid, nx, ny, visited):
                visited[nx][ny] = True
                queue.append(((nx, ny), steps + 1))
    
    return -1  # Return -1 if it's not possible to clean all dirt

def print_grid(grid):
    for row in grid:
        print(' '.join(row))
    print()

def main():
    grid = [
        ['C', '.', '.', '#', 'D'],
        ['.', '.', '.', '.', '.'],
        ['.', '#', '.', '#', '.'],
        ['D', '.', '.', '.', 'D']
    ]
    
    print("Initial grid:")
    print_grid(grid)
    
    steps = bfs_clean(grid)
    
    if steps != -1:
        print("All dirt cleaned in", steps, "steps.")
    else:
        print("Not possible to clean all dirt.")
    
    print("Final grid:")
    print_grid(grid)

if __name__ == "__main__":
    main()
