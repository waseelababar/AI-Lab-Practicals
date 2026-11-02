
# Lab 3: A* Search for the 8-Puzzle

## Objective
Implement the A* search algorithm from lecture and apply it to the 8-Puzzle using two heuristics — **Misplaced Tiles** and **Manhattan Distance** — and empirically compare how many nodes each one causes A* to expand[cite: 16].

---

## 5. Analysis & Answers to Questions

### 1. Table (Output from Cell 16)
| Scramble Depth | Misplaced Tiles | Manhattan Distance |
| :---: | :---: | :---: |
| **5** | 3.6 | 3.6 |
| **10** | 4.4 | 4.2 |
| **15** | 5.6 | 5.4 |
| **20** | 13.6 | 10.4 |

              

### 2. Chart Reference
  [Colab will keep the plot output attached to Cell 16 — reference it here, no need to duplicate it]

### 3. Answers:

* **At what scramble depth does the gap between the two heuristics become clearly visible? Why does the gap widen as depth increases rather than staying constant?**  
  The gap between the two heuristics becomes clearly visible at a deeper scramble depth (around **Depth 20**). The gap widens because as the puzzle becomes more scrambled, the number of possible states grows exponentially. Manhattan Distance provides a much closer estimation of the actual remaining steps than Misplaced Tiles, preventing unnecessary node expansions.

* **Manhattan Distance is provably ≥ Misplaced Tiles for every state. Using the lecture's definition of admissibility, explain why a higher admissible heuristic is not a violation of admissibility, and why it leads to fewer node expansions.**  
  An admissible heuristic never overestimates the true cost to reach the goal. Even though Manhattan Distance gives a higher (more accurate) value than Misplaced Tiles, it is still less than or equal to the actual shortest path cost, so it remains admissible. Because it is closer to the true cost, it gives better guidance to the A* algorithm, pruning away bad paths and resulting in fewer node expansions.

* **(Optional) Try increasing scramble depth until Misplaced Tiles becomes impractically slow. Does Manhattan Distance hit the same wall at the same depth?**  
  No, Manhattan Distance handles higher depths much more efficiently because it evaluates tile distances more precisely, meaning it hits performance limits (walls) much later than Misplaced Tiles.

---

## Submission Checklist
- [x] Notebook run top to bottom cleanly[cite: 18].
- [x] `get_neighbors`, `misplaced_tiles`, `manhattan_distance` implemented[cite: 18].
- [x] `a_star_search` implemented[cite: 18].
- [x] Comparison run across scramble depths[cite: 18].
- [x] Table and chart generated[cite: 18].
- [x] Section 5 analysis answered[cite: 18].
