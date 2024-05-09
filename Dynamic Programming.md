Dynamic programming is a technique used to solve problems by breaking them down into simpler subproblems and solving each subproblem only once, storing their solutions in a table (usually an array or a matrix). Here's an overview:

1. **Optimal Substructure**: Dynamic programming is applicable when the problem can be broken down into overlapping subproblems. That is, the problem can be solved by combining the solutions to the subproblems.

2. **Memoization**: This is a top-down approach where you store the results of expensive function calls and reuse them when the same inputs occur again. It involves creating a memo table to store the results of subproblems.

3. **Tabulation**: This is a bottom-up approach where you solve the problem by solving all subproblems first and storing their results in a table (usually an array or a matrix). This method does not involve recursion and is often more efficient in terms of space and time complexity.

4. **Examples**:
   - **Fibonacci Sequence**: The Fibonacci sequence is a classic example of a problem that can be solved using dynamic programming. Instead of recursively computing Fibonacci numbers, you can use memoization or tabulation to store previously computed values and avoid redundant computations.
   - **Knapsack Problem**: Given items with certain weights and values, the knapsack problem asks for the maximum value that can be obtained by selecting a subset of the items that fit into a knapsack of limited capacity. Dynamic programming can be used to solve this problem efficiently.
   - **Longest Common Subsequence**: Given two sequences, find the longest subsequence present in both of them. Dynamic programming can be used to solve this problem by breaking it down into simpler subproblems and storing their solutions.

5. **Time Complexity**: Dynamic programming solutions often result in improved time complexity compared to naive recursive approaches because they avoid redundant computations by storing intermediate results.

6. **Space Complexity**: Dynamic programming solutions may require additional space to store intermediate results, but this can often be optimized to use only a constant amount of extra space or to use space proportional to the input size.

Overall, dynamic programming is a powerful technique used to efficiently solve a wide range of problems in computer science, including optimization, string processing, and combinatorial problems.