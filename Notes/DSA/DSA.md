# BASIC TERMINOLOGY :
[[ALGORITHM]]
[[ALGORITHM ANALYSIS]]
[[TIME COMPLEXITY]]
[[SPACE COMPLEXITY]]
[[ASYMPTOTIC NOTATION]]
[[RECURSION]]

# ALGORITHMS : 
[[SORT]]
[[HASHING]]
[[DIVIDE AND CONQUER]]
[[Dynamic Programming]]
[[Greedy Method]]
[[BACKTRACKING - Brute Force]]
[[DFS]]
[[BFS]]
[[PRIM'S ALGO]]
[[KRUSKAL'S ALGO]]
[[FLOYD'S ALGO]]

# Data Structures :
[[ARRAYS]]
[[STACK]]
[[QUEUE]]
[[LINKED LIST]]
[[HASH TABLE]]
[[TREES]]
[[GRAPHS]]
[[SETS JS]]
[[MAPS JS]]

# MISC:
[[SPARSE MATRIX]]
[[BRANCH AND BOUND]]


# Techniques: 
[[TWO POINTER]]
[[SILDING WINDOW]]


#NOTE/DSA/COMPETITIVE-PROGRAMMING
- In competitive programming or in the platforms like Leetcode and GeeksforGeeks, we generally run our codes on online servers. Most of these servers execute roughly 10^8 operations in approximately 1 second i.e. 1s. We must be careful that if the time limit is given as 2s the operations in our code must be roughly 2*10^8, not 10^16. Similarly, 5s refers to 5*10^8. Simply, if we want our code to be run in 1s, the time complexity of our code must be around O(10^8) avoiding the constants and the lower values.