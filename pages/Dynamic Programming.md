- # Introduction: Stanford - cs97si
	- link: https://web.stanford.edu/class/cs97si/04-dynamic-programming.pdf
	- ## What is DP?
		- Wikipedia definition: “method for solving complex problems by breaking them down into simpler subproblems”
		- Steps for Solving DP Problems:
			- 1) Define subproblems
			- 2) Write down the recurrence that relates subproblems
			- 3) Recognize and solve the base cases
	- ## Examples
		- 1-dim DP Example: number of different ways to write n as the sum of 1, 3, 4
		  collapsed:: true
			- Problem: given $n$, find the number of different ways to write n as the sum of $1, 3, 4$
			- Define subproblems:
				- Let $D_n$ be the number of ways to write n as the sum of $1, 3, 4$
			- Find the recurrence:
				- Consider one possible solution $n = x_1 + x_2 + ... + x_m$
				- If $x_m$ = 1, the rest of the terms must sum to $n − 1$
				- Thus, the number of sums that end with $x_m = 1$ is equal to $D_{n−1}$
				- Take other cases into account ($x_m = 3$, $x_m = 4$)
			- Recurrence is then $D_n = D_{n−1} + D_{n−3} + D_{n−4}$
			- Solve the base case
				- $D_0 = 1$
				- $D_n = 0$ for all negative $n$
				- Alternatively, can set: $D_0 = D_1 = D_2 = 1$, and $D_3 = 2$
			- Implementation
				- ```
				  D[0] = D[1] = D[2] = 1; D[3] = 2;
				  for(i = 4; i <= n; i++)
				  	D[i] = D[i-1] + D[i-3] + D[i-4];
				  ```
		- 1-dim DP Example: POJ 2663 **Tri Tiling**
		  collapsed:: true
			- Problem: Given n, find the number of ways to fill a 3 × n board with dominoes
			- Define subproblems: Define $D_n$ as the number of ways to tile a $3 × n$ board
			- Find recurrence:
				- Consider different ways to fill the nth column
				- And see what the remaining shape is
		- 2-dim DP Example: Given two strings x and y, find the **longest common subsequence (LCS)** and print its length
			- Example:
				- x: ABCBDAB
				- y: BDCABC
				- “BCAB” is the longest subsequence found in both sequences, so the answer is 4
			- Define subproblems:
				- Let $D_{ij}$ be the length of the LCS of $x_{1...i}$ and $y_{1...j}$
			- Find the recurrence & base case
				- If $x_i = y_j$ , they both contribute to the LCS
					- $D_{ij} = D_{i−1,j−1} + 1$
				- Otherwise, either $x_i$ or $y_j$ does not contribute to the LCS, so one can be dropped
					- $D_{ij} = max \{D_{i−1,j} \ , \ D_{i,j−1}\}$
				- Find and solve the base cases:
					- $D_{i0} = D_{0j} = 0$
			- Implementation
				- ```
				  for(i = 0; i <= n; i++) D[i][0] = 0;
				  for(j = 0; j <= m; j++) D[0][j] = 0;
				  for(i = 1; i <= n; i++) {
				  	for(j = 1; j <= m; j++) {
				  		if(x[i] == y[j])
				  			D[i][j] = D[i-1][j-1] + 1;
				  		else
				  			D[i][j] = max(D[i-1][j], D[i][j-1]);
				  	}
				  }
				  ```
		- Interval DP Example: Create Palindrome
		  collapsed:: true
			- Problem: given a string $x = x_{1...n}$, find the minimum number of characters that need to be inserted to make it a palindrome
			- Example:
				- x: Ab3bd
				- Can get “dAb3bAd” or “Adb3bdA” by inserting 2 characters (one ‘d’, one ‘A’)
			- Define subproblems
				- Let $D_{ij}$ be the minimum number of characters that need to be inserted to make $x_{i...j}$ into a palindrome
				- Find the recurrence
					- Consider a shortest palindrome $y_{1...k}$ containing $x_{i...j}$
					- Either $y_1 = x_i$ or $y_k = x_j$ (why?)
					- $y_{2...k−1}$ is then an optimal solution for $x_{i+1...j}$ or $x_{i...j−1}$ or $x_{i+1...j−1}$
						- last case possible only if $y_1 = y_k = x_i = x_j$
					- $D_{ij} =$
						- $1 + min{Di+1,j , Di,j−1}$ für $xi \neq xj$
						- $D_{i+1,j−1}$ für $x_i = x_j$
			- Find and solve the base cases: $D_{ii} = D_{i,i−1} = 0$ for all $i$
			- Implementation
				- ```
				  // fill in base cases here
				  for(t = 2; t <= n; t++)
				  for(i = 1, j = t; j <= n; i++, j++)
				  	// fill in D[i][j] here
				  ```
				- Note how we use an additional variable t to fill the table in correct order
				- And yes, for loops can work with multiple variables
			- An Alternate Solution
				- Reverse $x$ to get $x^R$
				- The answer is $n − L$, where $L$ is the length of the LCS of $x$ and $x^R$
				- Exercise: Think about why this works
		- Tree DP Example: black leaves
		  collapsed:: true
			- Problem: given a tree, color nodes black as many as possible without coloring two adjacent nodes
			- Subproblems:
				- First, we arbitrarily decide the root node r
				- $B_v$: the optimal solution for a subtree having $v$ as the root, where we color $v$ black
				- $W_v$: the optimal solution for a subtree having $v$ as the root, where we don’t color $v$
				- Answer is $max\{B_r, W_r\}$
			- Find the recurrence
				- Crucial observation: once v’s color is determined, subtrees can be solved independently
				- If v is colored, its children must not be colored
					- $B_v = 1 + \sum_{u \in children(v)} W_u$
				- If v is not colored, its children can have any color
					- $W_v = 1 + \sum_{u∈children(v)} max{B_u, W_u}$
			- Base cases: leaf nodes
		- Subset DP Example: Traveling Salesman Problem
		  collapsed:: true
			- Problem: given a weighted graph with $n$ nodes, find the shortest path that visits every node exactly once
				- Wait, isn’t this an NP-hard problem?
					- Yes, but we can solve it in $O(n^22^n)$ time
					- Note: brute force algorithm takes $O(n!)$ time
			- Define subproblems
				- $D_{S,v}$: the length of the optimal path that visits every node in the set $S$ exactly once and ends at $v$
				- There are approximately $n2^n$ subproblems
				- Answer is $\min_{v∈V}D_{V,v}$, where $V$ is the given set of nodes
			- Let’s solve the base cases first
				- For each node $v$, $D_{\{v\},v} = 0$
			- Find the recurrence
				- Consider a path that visits all nodes in $S$ exactly once and ends at $v$
				- Right before arriving $v$, the path comes from some $u$ in $S − \{v\}$
				- And that subpath has to be the optimal one that covers $S − {v}$, ending at $u$
				- We just try all possible candidates for $u$
				- $D_{S,v} = \min_{u \in S- \{v\}} ( D_{S−\{v\},u} + cost(u, v) )$
			- Tip for implementation:
				- When working with subsets, it’s good to have a nice representation of sets
				- Idea: Use an integer to represent a set
					- Concise representation of subsets of small integers $\{0, 1, ...\}$
					- If the $i$th (least significant) digit is $1$, $i$ is in the set
					- If the $i$th digit is $0$, $i$ is not in the set
					- e.g., $19 = 010011_{(2)}$ in binary represent a set $\{0, 1, 4\}$
				- Using Bitmasks
					- Union of two sets $x$ and $y$: $x | y$
					- Intersection: $x \ \& \ y$
					- Symmetric difference: $x \ \hat{} \ y$
					- Singleton set $\{i\}$: $1 << i$
					- Membership test: $x \ \& \ (1 << i) != 0$
- # Vazirani, Algorithms Chapter 6
	- source: https://people.eecs.berkeley.edu/~vazirani/algorithms/chap6.pdf
	-
- # Homework
	- Vazirani, Algorithms 6.2
		- Problem: Travel Plan
			- You are going on a long trip. You start on the road at milepost 0. Along the way, there are n hotels, at mileposts $a_1 < a_2 < ... < a_n$, where each $a_i$ is measured from the starting point. The only places you are allowed to stop are at these hotels, but you can choose which of the hotels you stop at. You must stop at the final hotel (at distance $a_n$), which is your destination.
			- You’d ideally like to travel $200$ miles a day, but this may not be possible (depending on the spacing of the hotels). If you travel x miles during a day, the penalty for that day is $(200 − x)^2$. You want to plan your trip so as to minimize the total penalty - that is, the sum, over all travel days, of the daily penalties.
			- Give an efficient algorithm that determines the optimal sequence of hotels at which to stop
		-
	- Vazirani, Algorithms 6.3
		- Problem: Restaurants
			- Yuckdonald’s is considering opening a series of restaurants along Quaint Valley Highway (QVH). The $n$ possible locations are along a straight line, and the distances of these locations from the start of QVH are, in miles and in increasing order, $m_1, m_2, . . . , m_n$. The constraints are as follows:
				- At each location, Yuckdonald’s may open at most one restaurant. The expected profit from opening a restaurant at location $i$ is $p_i$ , where $p_i > 0$ and $i = 1, 2, . . . , n$.
				- Any two restaurants should be at least $k$ miles apart, where $k$ is a positive integer.
			- Give an efficient algorithm to compute the maximum expected total profit subject to the given constraints.
		-
	- Vazirani, Algorithms 6.4
		- Problem: A dictionary
			- You are given a string of $n$ characters $s[1 . . . n]$, which you believe to be a corrupted text document in which all punctuation has vanished (so that it looks something like “itwasthebestoftimes...”). You wish to reconstruct the document using a dictionary, which is available in the form of a Boolean function $dict(·)$: for any string $w$,
				- $$ dict(w) = \begin{cases}
				  true & \text{if } w \text{ is a valid word}\\
				  false & \text{otherwise}
				  \end{cases}$$
				- (a) Give a dynamic programming algorithm that determines whether the string $s[·]$ can be reconstituted as a sequence of valid words. The running time should be at most $O(n^2)$, assuming calls to $dict$ take unit time.
				- (b) In the event that the string is valid, make your algorithm output the corresponding sequence of words.
		-
	- Vazirani, Algorithms 6.7
		- Problem: palindromic
			- A subsequence is palindromic if it is the same whether read left to right or right to left. For instance, the sequence
				- $A, C, G, T, G, T, C, A, A, A, A, T, C, G$
			- has many palindromic subsequences, including $A, C, G, C, A$ and $A, A, A, A$ (on the other hand, the subsequence A, C, T is not palindromic). Devise an algorithm that takes a sequence $x[1 . . . n]$ and returns the (length of the) longest palindromic subsequence. Its running time should be $O(n^2)$.
		-
	- Vazirani, Algorithms 6.11
		- Problem: longest common subsequence
			- Given two strings $x = x_1 x_2 · · · x_n$ and $y = y_1 y_2 · · · y_m$, we wish to find the length of their longest common subsequence, that is, the largest $k$ for which there are indices $i1 < i2 < · · · < ik$ and $j_1 < j_2 < · · · < j_k$ with $x_{i_1} x_{i_2} · · · x_{i_k} = y_{j_1} y_{j_2} · · · y_{j_k}$. Show how to do this in time O(mn).
			-
	- Vazirani, Algorithms 6.17
		- Problem: denomination of a coin
			- Given an unlimited supply of coins of denominations $x_1, x_2, . . . , x_n$, we wish to make change for a value $v$; that is, we wish to find a set of coins whose total value is $v$. This might not be possible: for instance, if the denominations are $5$ and $10$ then we can make change for $15$ but not for $12$.
			- Give an $O(nv)$ dynamic-programming algorithm for the following problem.
				- Input: $x_1, . . . , x_n; v$.
				- Question: Is it possible to make change for $v$ using coins of denominations $x_1, . . . , x_n$?
		-