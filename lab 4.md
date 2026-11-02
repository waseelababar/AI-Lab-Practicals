
**Name:** Waseela Babar <br>
**Roll Number:** 08 <br>
**Batch:** 2024-2028 <br>
**Department:** Computer Science <br>
**Assignment:** AI <br>
**Submitted to:** Sir Imran <br>
**Date:** 2-Nov-2026

# Lab 4: Hill-Climbing Search with the N-Queens Problem

## Lab Questions

Answer the following questions in Markdown cells in notebook.

**Q 1: What is the purpose of the evaluation function in Hill-Climbing?**

The evaluation function measures the quality or 'goodness' of a state. It acts as a heuristic guide that tells the search algorithm which states are closer to the goal, allowing it to make local greedy decisions to move towards better states.

**Q 2: Why is an evaluation score of zero the best result in our N-Queens implementation?**

Our evaluation function is defined as -count_conflicts(state). Since the N-Queens objective is to have zero conflicts (no two queens threatening each other) and conflicts cannot be negative, the maximum possible value of -count_conflicts(state) is 0, indicating a perfect, conflict-free board state.

**Q 3: What is the difference between a local maximum and a global maximum?**

Local Maximum: A state that is better than all of its immediate neighbors, but is not the best possible overall state.
Global Maximum: The absolute best state possible across the entire state space (in our case, any state with an evaluation score of 0).

**Q 4: Why can basic Hill-Climbing stop without finding a solution even when a solution exists?**

Basic Hill-Climbing is a greedy local search algorithm that only moves to a neighbor if that neighbor has a strictly higher evaluation score. If it reaches a local maximum where no neighbor is better than the current state, the search terminates because it cannot escape without taking a downhill step.

**Q 5: Does reaching a local maximum always mean that the algorithm has failed? Explain.**

Yes, in the context of finding a perfect solution to the constraint satisfaction problem (N-Queens), reaching a local maximum with an evaluation score  <0  is a failure because the state still contains conflicts.

**Q 6: For N = 8, how many neighbors does each state have in our implementation?**

For an  N -Queens board where each queen is placed in a unique column, each queen (out of  N ) can be moved to any of the other  N−1  rows in its column. For  N=8 :
Neighbors=N×(N−1)=8×7=56 neighbors 

**Q7: What does the evaluation-score graph tell you about the behavior of Hill-Climbing?**

The graph shows that Hill-Climbing makes rapid progress initially, with the evaluation score increasing sharply in the first few iterations. However, it quickly flattens out and terminates within very few steps once it hits a local or global maximum, showing how short-sighted greedy local search is.

**Q 8: Explain probabilistic completeness in your own words.**

Probabilistic completeness means that if a solution exists, the probability that the algorithm will find it approaches 100% (or 1) as the number of independent random attempts (restarts) or run time approaches infinity.

**Q 9: Why does Random-Restart Hill-Climbing improve the chance of finding a solution?**

Because basic Hill-Climbing is highly dependent on the random starting point. By resetting the algorithm with a new random starting state when it gets stuck, it explores entirely different areas of the search space, giving it multiple independent trials to find a basin of attraction that leads to the global maximum.

**Q10: Does probabilistic completeness guarantee that a solution will be found within 100 restarts? Why or why not?**

No, it does not guarantee a solution within any finite boundary like 100 restarts. Probabilistic completeness is an asymptotic guarantee (as restarts  k→∞ ). For any finite  k , there is always a non-zero probability that all  k  independent runs will end in local maxima.


---
