# Lab 2

## Task: Compare BFS and DFS

**Topic:** Uninformed Search Algorithms

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

---py
directions = [
    (0, 1),    # right
    (1, 0),    # down
    (0, -1),   # left
    (-1, 0)    # up
]

# Run DFS again with the new direction order
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

# Understand what happened ?
 #  What did we change?

 Previously, your directions were:
 up, down, left, right

 Now we changed them to:

 right, down, left, up


### 2. Output

**DFS Path (New Order):** 
[(0,0), (1,0), (2,0), (2,1), (2,2), (3,2), (3,3), (3,4), (4,4)]

**DFS Path Length:** 8

**DFS Maximum Frontier:** 3

### 3. Answers to the Questions

**Q1. Did the DFS path change?**

Yes, the DFS path changed because we changed the order of directions. Previously, DFS explored the upper route, but with the new order, it explored the lower route.

**Q2. Did BFS's path (Section 4) depend on this ordering the same way? Why or why not?**

BFS also uses the neighbor order when exploring positions. Its selected path can change when multiple shortest paths are available. However, BFS always finds a shortest path when every movement has an equal cost. In this experiment, we only ran DFS again, so the original BFS result remained unchanged.

