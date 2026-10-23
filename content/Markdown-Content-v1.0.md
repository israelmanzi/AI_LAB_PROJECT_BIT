# Markdown Content v1.0

**Team 404: HINF** · Algorithms, Data Structures & Connectionist AI

This version defines arrays and linked lists, compares their operation costs, and implements a queue as a linked list.

## Contents

- [Arrays and Linked Lists](#11-arrays-and-linked-lists)
- [Queues and Stacks](#12-queues-and-stacks)
- [References](#references)

## 1.1 Arrays and Linked Lists

### Learning outcomes

- Define an array and a linked list.
- Compute the address of an array element from its index.
- Explain how access, search, insertion and deletion work in each structure.
- Select an appropriate structure for a given set of operations.

### Data structure

A **data structure** is a collection of data values, the relationships among them, and the operations that can be performed on them. It determines how data is laid out in memory and which operations are efficient.

### Array

**Definition.** An array is a contiguous block of memory that stores a fixed number of elements of the same data type, with each element accessible by its index.

Properties:

- **Contiguous allocation.** Elements occupy consecutive memory cells.
- **Homogeneous elements.** Every element has the same type and size.
- **Random access.** The address of element `i` is calculated directly:

```
address(i) = base address + i × element size
```

Indexes start at 0. If an array starts at address 1000 and each element occupies 4 bytes, element 3 is at `1000 + 3 × 4 = 1012`.

