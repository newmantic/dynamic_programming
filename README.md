# dynamic_programming

Dynamic Programming (DP) is a method used to solve complex problems by breaking them down into simpler subproblems. It is particularly useful for optimization problems where the solution can be constructed from solutions to subproblems.


Optimal Substructure:
A problem has an optimal substructure if an optimal solution to the problem can be constructed efficiently from optimal solutions to its subproblems.
If S = optimal solution to problem P,
Then S can be composed of optimal solutions to subproblems P1, P2, ..., Pn.

Overlapping Subproblems:
A problem has overlapping subproblems if the same subproblems are solved multiple times during the execution of the algorithm.
If solving problem P involves solving subproblems P1, P2, ..., Pn multiple times,
Then P has overlapping subproblems.


Memoization is a technique used to store the results of subproblems to avoid redundant computations. It is often implemented using a table (or dictionary) to store results of solved subproblems.
memo_table[i] = solution to subproblem i

Tabulation is a bottom-up approach where solutions to subproblems are computed iteratively and stored in a table. The final solution is obtained by combining the results from the table.
dp[i] = solution to subproblem i computed iteratively


The dynamic programming approach generally follows these steps:
1) Define the structure of the optimal solution:
Identify how to express the solution to the problem in terms of solutions to its subproblems.
2) Recursively define the value of the optimal solution:
Write a recursive relation (often called a recurrence relation) that defines the solution in terms of smaller subproblems.
3) Compute the value of the optimal solution (usually in a bottom-up manner):
Use memoization or tabulation to solve the subproblems and store their results.
4) Construct the optimal solution:
If needed, construct the optimal solution using the stored results from the subproblems.


The Fibonacci sequence is defined as:
F(0) = 0
F(1) = 1
F(n) = F(n-1) + F(n-2) for n >= 2

Recursive Approach (without DP):
fib(n):
    if n <= 1:
        return n
    else:
        return fib(n-1) + fib(n-2)
This approach has exponential time complexity O(2^n) because it recomputes the same subproblems multiple times.

Dynamic Programming Approach (with Memoization):
fib(n, memo):
    if n <= 1:
        return n
    if memo[n] != -1:
        return memo[n]
    memo[n] = fib(n-1, memo) + fib(n-2, memo)
    return memo[n]
Here, memo is an array initialized to -1 to indicate that the subproblems have not been solved yet. The time complexity of this approach is O(n).

Dynamic Programming Approach (with Tabulation):
fib(n):
    dp = [0] * (n+1)
    dp[0] = 0
    dp[1] = 1
    for i in range(2, n+1):
        dp[i] = dp[i-1] + dp[i-2]
    return dp[n]
    
This tabulation approach also has a time complexity of O(n) but uses an iterative method to fill the table.
