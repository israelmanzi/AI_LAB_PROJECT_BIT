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

### Static and dynamic arrays

**Static array.** An array with a fixed size determined at compile time. The size cannot be changed during runtime.

**Dynamic array.** An array whose size can be changed during runtime. When full, it allocates a larger block of memory and copies the existing elements into it.

A dynamic array tracks two quantities:

- **Size**: the number of elements currently stored.
- **Capacity**: the number of elements the allocated block can hold.

When an append would exceed the capacity, the array allocates a larger block, usually twice the current capacity, copies the existing elements, and then writes the new element.

#### Example: growth by doubling

| Operation | Size | Capacity | Elements                      | Work                         |
| --------- | ---- | -------- | ----------------------------- | ---------------------------- |
| append 10 | 1    | 2        | `10, _`                       | write 10                     |
| append 20 | 2    | 2        | `10, 20`                      | write 20                     |
| append 30 | 3    | 4        | `10, 20, 30, _`               | allocate 4, copy 2, write 30 |
| append 40 | 4    | 4        | `10, 20, 30, 40`              | write 40                     |
| append 50 | 5    | 8        | `10, 20, 30, 40, 50, _, _, _` | allocate 8, copy 4, write 50 |

![Dynamic array growth by doubling](assets/images/1.1-dynamic-array.png)
_Solid cells hold elements. Dashed cells are allocated but unused. A resize allocates a new block and copies every existing element._

### Linked list

**Definition.** A linked list is a linear collection of nodes, each containing a data field and a pointer to the next node. Nodes are allocated independently and need not occupy contiguous memory.

Properties:

- The first node is the **head**. The last node's pointer is `null`.
- Elements are reached by following pointers from the head, so access by position is sequential.
- A **singly linked list** stores one pointer per node. A **doubly linked list** stores pointers to both the next and previous nodes. A **circular linked list** connects the last node back to the head.

**Operations and how to perform them:**

| Operation                          | How it is done                                                                                                             |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Access the element at position k   | Start at the head and follow the next pointer k times, then return the data field of that node.                            |
| Search for a value                 | Start at the head and compare each node's data with the value until it matches or the list ends.                           |
| Insert at the head                 | Create a node. Set its next pointer to the current head, then set head to the new node.                                    |
| Insert after a known node          | Create a node. Set its next pointer to the known node's next node, then set the known node's next pointer to the new node. |
| Insert at position k               | Traverse to the node at position k - 1, then insert the new node after it.                                                 |
| Delete the head                    | Set head to the current head's next pointer.                                                                               |
| Delete the node after a known node | Set the known node's next pointer to the node after the one being deleted.                                                 |
| Delete the node at position k      | Traverse to the node at position k - 1, then delete the node after it.                                                     |

