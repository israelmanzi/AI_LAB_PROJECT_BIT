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

### Worked example: insert 15 at index 3

**Array.** The array has one free slot. Inserting at index 3 moves the elements at indexes 3, 4 and 5 one position right, then writes 15 into index 3.

![Array insertion](assets/images/1.1-array-insert.png)
_The three elements after the insertion point shift right. The new element fills index 3._

**Linked list.** The new node goes after the node containing 30. Two pointers change: the new node points to 40, then 30 points to the new node.

![Linked-list insertion](assets/images/1.1-linked-insert.png)
_Step 1 links the new node to the rest of the list. Step 2 links 30 to the new node. No other node moves._

The order matters. If 30 pointed to 15 first, the only reference to 40 would be lost.

### Visual

> How the data structures are stored out in memory.

![Array and linked list in memory](assets/images/1.1-array-vs-linked-list.png)
_The array occupies consecutive addresses that differ by the element size. The linked list nodes are non-contiguous, and their logical order is defined only by the pointers._

### Activity: choose a structure for a music playlist

You are building a music playlist app. Users can jump to a track by its position number, add a song at the end, and occasionally insert a song in the middle after dragging it. The number of songs is not known in advance.

1. Choose an array or a linked list for the playlist. Justify the choice using how often each operation happens, not just the operation names.
2. Describe one practical problem the other structure would cause in this app.
3. The app must let a user jump instantly to track 500 in a playlist of 10,000 songs. Which structure is more practical, and why?

**Expected outcome:** a dynamic array is the practical choice. Jumping to a numbered track is direct, and most playback is sequential, so the occasional middle insertion is acceptable even though later songs must shift. The array also grows automatically in most languages. A linked list is practical when songs are inserted or removed at known positions very often and users navigate one track at a time. Jumping to track 500 would require walking through the list, and every node stores an extra pointer. For the instant jump requirement, the array is clearly better.

### Check your understanding

**Q1 (True/False).** In an array of 1,000,000 elements, reading element 999,999 takes about the same time as reading element 0.

**Q2 (True/False).** Binary search can be performed efficiently on a sorted singly linked list.

**Q3 (Multiple choice).** An array of 4-byte integers starts at address 2000. What is the address of element 5?

A. 2005 B. 2020 C. 2024 D. 2016

**Q4 (Multiple choice).** Which operation takes a small, fixed number of steps for a linked list but requires moving many elements in an array?

A. Access by index B. Insertion at the head C. Search for a value D. Finding the maximum element

**Q5 (Problem).** The array `[4, 8, 15, 16, 23, 42]` has capacity for one more element. Show the shifts required to insert 10 at index 2, and state the number of elements moved.

**Q6 (Problem).** For the linked list `10 -> 20 -> 30 -> 40`, describe the pointer assignments required to insert 25 between 20 and 30. Explain how the node containing 20 is found.

### Answers

**A1.** True. The address is calculated with one formula, so the algorithm can reach any index directly, without walking through earlier elements.

**A2.** False. Binary search needs to jump straight to the middle element. A linked list has no direct jump, so the algorithm must walk from the head to the middle one node at a time. The halving advantage is lost.

**A3.** B. `2000 + 5 × 4 = 2020`.

**A4.** B. Inserting at the head changes one pointer. An array must move every existing element one slot to the right.

**A5.** Shift 42 from index 5 to 6, 23 from 4 to 5, 16 from 3 to 4, and 15 from 2 to 3, then write 10 at index 2. Result: `[4, 8, 10, 15, 16, 23, 42]`. Four elements move.

**A6.** Allocate a node containing 25. Set its next pointer to the node containing 30. Set the next pointer of the node containing 20 to the new node. To find 20, start at the head and follow the pointers one node at a time until you reach it.

