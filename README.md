Download link :https://programming.engineering/product/homework-1-question-1-search-trees/


# Homework-1-Question-1-Search-Trees
Homework 1 Question 1: Search Trees
Question 1: Search Trees

How many nodes are in the complete search tree for the given state space graph? The start state is S. You may find it helpful to draw out the search tree on a piece of paper.

Question 2: Depth-First Graph Search

Consider a depth-first graph search on the graph below, where S is the start and G is the goal state. Assume that ties are broken alphabetically (so a partial plan S->X->A would be expanded before S->X->B and S->A->Z would be expanded before S->B->A). You may find it helpful to execute the search on scratch paper.

Please write down the final path returned by depth-first graph search. Your answer should be a string with S as your first character and G as your last character. Don’t include arrows or spaces in your submission. For example, if you believe the path is S->X->G, please write SXG.

Question 3: Breadth-First Graph Search

Consider a breadth-first graph search on the graph below, where S is the start and G is the goal state. Assume that ties are broken alphabetically (so a partial plan S->X->A would be expanded before S->X->B and S->A->Z would be expanded before S->B->A). You may find it helpful to execute the search on scratch paper.

Please write down the final path returned by breadth-first graph search. Your answer should be a string with S as your first character and G as your last character. Don’t include arrows or spaces in your submission. For example, if you believe the path is S->X->G, please write SXG.

Question 4: A* Graph Search

Consider A* graph search on the graph below. Arcs are labeled with action costs and states are labeled with heuristic values. Assume that ties are broken alphabetically (so

partial plan S->X->A would be expanded before S->X->B and S->A->Z would be expanded before S->B->A.

In what order are states expanded by A* graph search? You may find it helpful to execute the search on scratch paper. please write down SXG.

What path does A* graph search return?

Hive Minds

The next five questions share a common setup. You control one or more insects in a rectangular maze-like environment with dimensions M×N, as shown in the figure below.

At each time step, an insect can move into an adjacent square if that square is currently free, or the insect may stay in its current location. Squares may be blocked by walls, but the map is known. Optimality is always in terms of time steps; all actions have cost 1 regardless of the number of insects moving or where they move.

For each of the five questions, you should answer for a general instance of the problem, not simply for the example maps shown.


Question 5: Hive Minds: Lonely Bug

You control a single insect as shown in the maze below, which must reach a designated target location X, also known as the hive. There are no other insects moving around.


Which of the following is a minimal correct state space representation?

A. An integer d encoding the Manhattan distance to the hive.

B. A tuple (x, y) encoding the x and y coordinates of the insect.

C. A tuple (x, y, d) encoding the insect’s x and y coordinates as well as the Manhattan distance to the hive.

D. This cannot be represented as a search problem.

What is the size of the state space?


( )2

2



max( , )

Which of the following heuristics are admissible (if any)?

A. Manhattan distance from the insect’s location to the hive.

B. Euclidean distance from the insect’s location to the hive.

C. Number of steps taken by the insect.

Question 6: Hive Minds: Swarm Movement

You control insects, each of which has a specific target ending location . No two insects may occupy the same square. In each time step all insects move simultaneously to a currently free square (or stay in place); adjacent insects cannot swap in a single time step.


Which of the following is a minimal correct state space representation?

tuples (( 1, 1), ( 2, 2), … , ( , )) encoding the and coordinates of each insect.

tuples (( 1, 1), ( 2, 2), … , ( , )) encoding theandcoordinates of

each insect, plus boolean variables indicating whether each insect is next to another insect.

tuples (( 1, 1), ( 2, 2), … , ( , )) encoding theandcoordinates of

each insect, plus booleans indicating which squares are currently occupied by an insect.

booleans ( 1, 2, … ,) encoding whether or not an insect is in each square.

What is the size of the state space?


2


( )

( ) 2

( ) 2

2

2Which of the following heuristics are admissible (if any)?

A. Sum of Manhattan distances from each insect’s location to its target location.

B. Sum of costs of optimal paths for each insect to its goal if it were acting alone in the environment, unobstructed by the other insects.

C. Max of Manhattan distances from each insect’s location to its target location.

D. Max of costs of optimal paths for each insect to its goal if it were acting alone in the environment, unobstructed by the other insects.

E. Number of insects that have not yet reached their target location.

Question 7: Hive Minds: Lost at Night

It is night and you control a single insect. You know the maze, but you do not know what square the insect will start in. You must pose a search problem whose solution is an all-purpose sequence of actions such that, after executing those actions, the insect will be on the exit square, regardless of initial position. The insect executes the actions mindlessly and does not know whether its moves succeed: if it uses an action which would move it in a blocked direction, it will stay where it is. For example, in the maze below, moving right twice guarantees that the insect will be at the exit regardless of its starting position.


Which of the following state representations could be used to solve this problem?

A. A tuple ( , ) representing the position of the insect.

B. A tuple ( , ) representing the position of the insect, plus a list of all squares visited by the insect.

C. An integer representing how many time steps have passed, plus an integer representing how many times the insect’s motion has been blocked by a wall.

D. A list of boolean variables, one for each position in the maze, indicating whether the insect could be in that position.

E. A list of all positions the insect has been in so far.

What is the size of the state space?



2

( )

2

The state space is infinite.

Which of the following are admissible heuristics?

A. Total number of possible locations the insect might be in.

B. The maximum of Manhattan distances to the goal from each possible location the insect could be in.

C. The minimum of Manhattan distances to the goal from each possible location the insect could be in.

Question 8: Early Goal Checking Graph Search

Recall from lecture the general algorithm for GRAPH-SEARCH reproduced below.


With the above implementation a node that reaches a goal state may sit on the fringe while the algorithm continues to search for a path that reaches a goal state. Let’s consider altering the algorithm by testing whether a node reaches a goal state when inserting into the fringe. Concretely, we add the line of code highlighted below:

Now, we’ve produced a graph search algorithm that can find a solution faster. However, In doing so we might have affected some properties of the algorithm. To explore the possible differences, consider the example graph below.


node expansion strategy, which path, if any, will the algorithm return?

If using EARLY-GOAL-CHECKING-GRAPH-SEARCH with an A* node expansion strategy, which path, if any, will the algorithm return?

Assume you run EARLY-GOAL-CHECKING-GRAPH-SEARCH with the Uniform Cost node expansion strategy, select all statements that are true.

The EXPAND function can be called at most once for each state.

The algorithm is complete.

The algorithm will return an optimal solution.

Assume you run EARLY-GOAL-CHECKING-GRAPH-SEARCH with the A* node expansion strategy and a consistent heuristic, select all statements that are true.

The EXPAND function can be called at most once for each state.

The algorithm is complete.

The algorithm will return an optimal solution.

Question 9: Lookahead Graph Search

Recall from lecture the general algorithm for Graph Search reproduced below.


Using GRAPH-SEARCH, when a node is expanded it is added to the closed set. This means that even if a node is added to the fringe multiple times it will not be expanded more than once. Consider an alternative version of GRAPH-SEARCH, LOOKAHEAD-GRAPH-SEARCH, which saves memory by using a “fringe-closed-set” keeping track of which states have been on the fringe and only adding a child node to the fringe if the state of that child node has not been added to it at some point. Concretely, we replace the highlighted block above with the highlighted block below.


Now, we’ve produced a more memory efficient graph search algorithm. However, in doing so, we might have affected some properties of the algorithm. To explore the possible differences, consider the example graph below.


If using LOOKAHEAD-GRAPH-SEARCH with an A* node expansion strategy, which path will this algorithm return? (We strongly encourage you to step through the execution of the algorithm on a scratch sheet of paper and keep track of the fringe and the search tree as nodes get added to the fringe.)

Assume you run LOOKAHEAD-GRAPH-SEARCH with the A* node expansion strategy and a consistent heuristic, select all statements that are true.

The EXPAND function can be called at most once for each state.

The algorithm is complete.

The algorithm will return an optimal solution.
