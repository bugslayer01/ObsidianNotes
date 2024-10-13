

> [!PDF|note] [[Single Linked List.pdf#page=1&selection=0,6,2,4&color=note|Single Linked List, p.1]]
> > Linked List


# Singly Linked List

A **linked list** is a linear data structure where elements are stored in nodes, and each node points to the next node in the sequence. Unlike arrays, where elements are stored in contiguous memory locations, linked lists store elements in a non-contiguous manner, with each element pointing to the next one via a reference or pointer.

### Key Components of a Linked List:
1. **Node**: Each node contains two parts:
   - **Data**: The value or data stored in the node.
   - **Next**: A pointer/reference to the next node in the list.
   
2. **Head**: A reference to the first node in the linked list. If the list is empty, the head is `null` or `None`.

3. **Tail**: The last node in the linked list points to `null` (or `None`), indicating the end of the list.

## Types of Linked Lists:
1. **Singly Linked List**: Each node points only to the next node.
   - Example: `Node1 -> Node2 -> Node3 -> null`

2. **Doubly Linked List**: Each node contains a reference to both the next and the previous node, allowing traversal in both directions.
   - Example: `null <- Node1 <-> Node2 <-> Node3 -> null`

3. **Circular Linked List**: The last node points back to the first node instead of `null`, forming a circular chain.
   - Example (Singly): `Node1 -> Node2 -> Node3 -> Node1`

## Basic Operations:
- **Insertion**: Adding a node at the beginning, end, or any specific position in the list.
- **Deletion**: Removing a node from the list.
- **Traversal**: Visiting each node in the list to access data.
- **Search**: Finding a node with a specific value.

## Advantages of Linked Lists:
- Efficient insertions and deletions (especially compared to arrays, as elements don’t need to be shifted).
  
## Disadvantages of Linked Lists:
- Less efficient for random access because you have to traverse the list to find a specific element.
> [!PDF|red] [[Single Linked List.pdf#page=7&selection=20,0,32,4&color=red|Single Linked List, p.7]]
> > Pictorial representation of a singly linked list

## Exception Cases to Check for Linked List Operations

## 1. Insert at Start
- **Case 1**: List is empty (`head == nullptr`).

---

## 2. Insert at End
- **Case 1**: List is empty (`head == nullptr`).
- **Case 2**: List has only one node (`head->next == nullptr`).

---

## 3. Delete at Start
- **Case 1**: List is empty (`head == nullptr`).
- **Case 2**: List has only one node (`head->next == nullptr`).

---

## 4. Delete at End
- **Case 1**: List is empty (`head == nullptr`).
- **Case 2**: List has only one node (`head->next == nullptr`).

---

## 5. Search
- **Case 1**: List is empty (`head == nullptr`).
- **Case 2**: Target value not found.

---

## 6. Display
- **Case 1**: List is empty (`head == nullptr`).

---

## 7. Insert After a Specific Value
- **Case 1**: List is empty (`head == nullptr`).
- **Case 2**: Value not found in the list.

---

## 8. Delete a Specific Node
- **Case 1**: List is empty (`head == nullptr`).
- **Case 2**: Node to be deleted is the head node (`head->val == val`).
- **Case 3**: Node to be deleted is not found.
- **Case 4**: List has only one node (`head->next == nullptr`).

___

# Doubly linkedlist(not in mst )

> [!PDF|] [[Doubly and Circular Linked List.pdf#page=1&selection=0,0,4,4|Doubly and Circular Linked List, p.1]]
> > Doubly Linked List

# Circular linked list
> [!PDF|note] [[Doubly and Circular Linked List.pdf#page=24&selection=0,0,4,4&color=note|Doubly and Circular Linked List, p.24]]
> > Circular Linked List

