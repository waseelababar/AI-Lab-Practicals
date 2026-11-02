# Lab 2

**Topic:** Uninformed Search Algorithms


## Task: Compare BFS and DFS


### Comparison Table

| Algorithm | Path Length | Maximum Frontier |
| :--- | :---: | :---: |
| **BFS** | 8 | 3 |
| **DFS** | 8 | 3 |

---

### Answers to the Questions

**Q1. Which algorithm found the shorter path?**  
Both algorithms found paths of equal length. BFS and DFS each found a path of 8 steps.

**Q2. Which algorithm had the larger maximum frontier?**  
Neither algorithm had a larger maximum frontier. Both algorithms had a maximum frontier of 3.

**Q3. Why did the two algorithms produce different paths on the same maze?**  
BFS explores the maze level by level, while DFS explores one direction deeply before trying another direction. Therefore, they produce different paths.


# Experiment 1 — Change the Neighbor Order.

### 1. Objective

The objective of this experiment is to test how changing the order of directions (neighbors) affects the path found by Depth-First Search (DFS). Because DFS explores deep paths based on the sequence of available directions (up, down, left, right), changing this order will alter the resulting path.
### 💻 Code Cell

# ```python
directions = [
    (0, 1),   # right
    (1, 0),   # down
    (0, -1),  # left
    (-1, 0)   # up
]

dfs_path2, dfs_frontier2 = dfs(maze, start, goal)

print("DFS path (new order):", dfs_path2)
print("DFS path length:", len(dfs_path2) - 1)
print("DFS maximum frontier:", dfs_frontier2)

print()
print_maze(maze, dfs_path2)


# Reset directions to the original order
directions = [
    (-1, 0),   # up
    (1, 0),    # down
    (0, -1),   # left
    (0, 1)     # right
]
---
