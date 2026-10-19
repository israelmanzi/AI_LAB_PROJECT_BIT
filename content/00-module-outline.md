# Module Outline: Algorithms, Data Structures & Connectionist AI

**Main idea:** *Part 1 shows how computers follow steps that people write. Part 3 shows how neural networks find their own steps by learning from data. Part 2 covers how data is organised, which both depend on.*

## Prerequisites

- School algebra: variables, simple equations, reading a graph
- No programming experience. Pseudocode is introduced in 1.1, and short Python snippets are optional.

## Learning outcomes

By the end, a beginner can:

1. Describe an algorithm in pseudocode and explain how it differs from a program.
2. Compare algorithms using Big-O and justify which is faster for large inputs.
3. Choose a design strategy (brute force, greedy, divide and conquer, dynamic programming) for a simple problem.
4. Trace linear search, binary search, and at least two sorting algorithms on a small list.
5. Choose a suitable data structure (array, linked list, stack, queue, hash table, tree, heap, graph) for a given task and explain why.
6. Explain how connectionist AI differs from rule-based (symbolic) AI, and supervised from unsupervised learning.
7. Calculate a perceptron's output by hand and explain why a single perceptron cannot learn XOR.
8. Describe how a neural network learns using loss and gradient descent (intuition, not full calculus).
9. Recognise overfitting and explain why we split data into training and test sets.

## Topic sequence and status

| # | Topic | Depth | Planned example / activity | Status |
|---|---|---|---|---|
| **Part 1** | **Algorithms** | | | |
| 1.1 | [What is an algorithm?](part1-algorithms/1.1-what-is-an-algorithm.md) | Detailed | Find the largest number in a list | outline only |
| 1.2 | [Measuring efficiency: Big-O](part1-algorithms/1.2-big-o.md) | Detailed | Step counts for n = 10 vs 1,000,000 | outline only |
| 1.3 | [Searching: linear and binary](part1-algorithms/1.3-searching.md) | Detailed | Guess a number from 1–100 in ≤ 7 tries | outline only |
| 1.4 | [Sorting](part1-algorithms/1.4-sorting.md) | Detailed | Sort a hand of cards; trace merge sort | outline only |
| 1.5 | [Recursion](part1-algorithms/1.5-recursion.md) | Brief | Factorial and the call stack | outline only |
| 1.6 | [Algorithm design strategies](part1-algorithms/1.6-design-strategies.md) | Brief | Greedy coin change that fails; Fibonacci with memoisation | outline only |
| **Part 2** | **Data Structures** | | | |
| 2.1 | [Arrays and linked lists](part2-data-structures/2.1-arrays-linked-lists.md) | Detailed | Cinema seats vs a treasure hunt | outline only |
| 2.2 | [Stacks and queues](part2-data-structures/2.2-stacks-queues.md) | Detailed | Undo button; bracket matching | outline only |
| 2.3 | [Hash tables](part2-data-structures/2.3-hash-tables.md) | Detailed | Hash names into 7 buckets | outline only |
| 2.4 | [Trees, BSTs and heaps](part2-data-structures/2.4-trees.md) | Detailed | Build a BST from 8 numbers; min-heap for triage | outline only |
| 2.5 | [Graphs, BFS and DFS](part2-data-structures/2.5-graphs.md) | Brief | Fewest stops on a metro map; when Dijkstra is needed | outline only |
| **Part 3** | **Connectionist AI** | | | |
| 3.1 | [From rules to learning](part3-connectionist-ai/3.1-rules-to-learning.md) | Detailed | Spam filter: rules vs learned; supervised vs unsupervised | outline only |
| 3.2 | [The perceptron](part3-connectionist-ai/3.2-perceptron.md) | Detailed | Hand-compute AND; learn OR | outline only |
| 3.3 | [Multi-layer networks and the forward pass](part3-connectionist-ai/3.3-multilayer-networks.md) | Detailed | 2-2-1 network that solves XOR | outline only |
| 3.4 | [How networks learn: loss and gradient descent](part3-connectionist-ai/3.4-learning.md) | Detailed | Walk downhill in fog; 3 steps by hand | outline only |
| 3.5 | [Training in practice: data and overfitting](part3-connectionist-ai/3.5-training-practice.md) | Detailed | TensorFlow Playground demo | outline only |
| 3.6 | [Deep learning today: CNNs, RNNs, Transformers](part3-connectionist-ai/3.6-deep-learning-today.md) | Brief | Match architecture to task | outline only |

## Links between the three parts

| Connectionist idea | Built on |
|---|---|
| Weights stored as a matrix | Arrays (2.1) |
| A network is a weighted, directed graph | Graphs (2.5) |
| Training is an algorithm that repeats until the error stops falling | Algorithms (1.1), Big-O (1.2) |
| Backpropagation moves backwards through layers | Graph traversal (2.5) |

## Scope boundaries

- **Detailed:** Big-O, searching, sorting, core data structures, perceptron, forward pass, gradient descent.
- **Brief intro only:** recursion, design strategies, heaps, Dijkstra (named, not traced), backpropagation maths, modern architectures.
- **Out of scope:** formal proofs, calculus derivations, programming-language specifics.

## Gaps and uncertainties

- Overlap with the *Big Data & Connectionist AI* team: confirm with the teacher how deep Part 3 should go.
- Recursion and graphs may need trimming if time is short.
- Topic owners not yet assigned.
