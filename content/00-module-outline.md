# Module Outline: Algorithms, Data Structures & Connectionist AI

## Prerequisite knowledge

- Algebra I.
- No programming experience required.
- Ability to read and understand simple concepts and think of problems, solutions and applications in real life.

## Intended learning outcomes

A beginner at the end of this journey should be able to:

1. Describe an algorithm by definition, pseudocode or code and explain how it differs from a program.
2. Compare algorithms using Big-O and decide which is faster for a large input.
3. Choose a suitable design strategy for a simple problem and justify the choice.
4. Trace linear search, binary search and at least two sorting algorithms on any given list/set.
5. Choose a suitable data structure for any problem and explain the choice.
6. Explain how connectionist AI differs from rule-based AI, and how supervised learning differs from unsupervised learning.
7. Explain the concept of a perceptron and how it makes decisions.
8. Explain why one perceptron cannot learn XOR.
9. Describe how a network learns using loss and gradient descent, at the level of intuition.
10. Recognise overfitting and explain why data is split into training and test sets.

## Topics and subtopics

Status labels: `outline only`, `drafted`, `checked`, `needs revision`.

### Part 1: Algorithms

| #   | Topic                               | Subtopics                                                                                             | Planned example/activity                                                      | Status       |
| --- | ----------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ------------ |
| 1.1 | What Is an Algorithm?               | Definition, properties; algorithm vs program; pseudocode; flowcharts; sequence, selection, repetition | Largest number in a list; flowchart                                           | drafted |
| 1.2 | Measuring Efficiency: Big-O         | Step counting; O(1), O(log n), O(n), O(n log n), O(n²); worst case; constants                         | Step counts at n = 10, 1k, 1M; rank snippets                                  | outline only |
| 1.3 | Searching: Linear and Binary Search | Linear; binary; sorted-list requirement; O(n) vs O(log n)                                             | Trace 23 in a 10-item list; guess 1-100 in 7 tries; odd length, missing value | drafted |
| 1.4 | Sorting                             | Selection, insertion; merge; divide and conquer; O(n²) vs O(n log n)                                  | Merge sort [38, 27, 43, 3, 9, 82, 10]; card sort                              | outline only |
| 1.5 | Recursion                           | Base case; recursive case; call stack; factorial, sum                                                 | factorial(4) call stack                                                       | outline only |
| 1.6 | Algorithm Design Strategies         | Brute force; greedy; divide and conquer; dynamic programming; memoisation                             | Coin change {1, 3, 4}, amount 6; Fibonacci naive vs memoised                  | outline only |

### Part 2: Data Structures

| #   | Topic                                | Subtopics                                                                             | Planned example/activity                               | Status       |
| --- | ------------------------------------ | ------------------------------------------------------------------------------------- | ------------------------------------------------------ | ------------ |
| 2.1 | Arrays and Linked Lists              | Contiguous storage; indexing; nodes, pointers; access, insert, delete costs; matrices | Insert into array vs linked list; weight matrix        | drafted |
| 2.2 | Stacks and Queues                    | LIFO, FIFO; push, pop, enqueue, dequeue; applications                                 | Bracket check; undo, printer queue                     | drafted |
| 2.3 | Hash Tables                          | Hash functions; buckets; collisions, chaining; O(1) average                           | Five names mod 7; collisions                           | outline only |
| 2.4 | Trees, Binary Search Trees and Heaps | Tree terms; BST insert/search; balanced vs degenerate; heaps, priority queues         | BST from [50, 30, 70, 20, 40, 60, 80]; min-heap triage | outline only |
| 2.5 | Graphs, BFS and DFS                  | Nodes, edges, adjacency lists; BFS; DFS; weighted graphs, Dijkstra                    | Metro fewest stops; 9 km vs 7 km                       | drafted |

### Part 3: Connectionist AI

| #   | Topic                                         | Subtopics                                                                                        | Planned example/activity                          | Status       |
| --- | --------------------------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------- | ------------ |
| 3.1 | From Rules to Learning                        | Symbolic vs connectionist; biological vs artificial neuron; supervised vs unsupervised; timeline | Spam rules vs learned; classify tasks             | drafted |
| 3.2 | The Perceptron                                | Weighted sum; bias; step function; decision boundary; learning rule; epochs; XOR limit           | AND by hand; learn OR in 4 epochs; XOR impossible | outline only |
| 3.3 | Multi-layer Networks and the Forward Pass     | Input, hidden, output layers; forward pass; matrix form; sigmoid, ReLU                           | 2-2-1 network for XOR                             | outline only |
| 3.4 | How Networks Learn: Loss and Gradient Descent | Loss; gradient descent; learning rate; backprop intuition                                        | Minimise w² from 4, n = 0.25 and 1.1              | outline only |
| 3.5 | Training in Practice: Data and Overfitting    | Train/test split; overfitting, underfitting; generalisation; remedies                            | TensorFlow Playground; label 3 loss curves        | outline only |
| 3.6 | Deep Learning Today: CNNs, RNNs, Transformers | CNNs; RNNs; transformers; applications; limitations                                              | Match 5 applications to architectures             | outline only |

## Gaps and uncertainties

- References partly checked; chapter numbers unconfirmed.
- Figures planned for most topics; only a few drawn.
- Depth of Part 3 to confirm with the teacher (overlap with Big Data & Connectionist AI).
- 1.5, 1.6, 2.5 and 3.6 are brief by design.
