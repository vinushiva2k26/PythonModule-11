# 📝 Doubly Linked List: Search an Element

This Python program demonstrates the implementation of a **Doubly Linked List** where you can insert elements at both the beginning and the end of the list. Additionally, it allows you to search for a specific element in the list.

---

## 🎯 Aim

To write a Python program that:
- Implements a **Doubly Linked List** with functions to insert elements at the beginning and the end of the list.
- Implements a search function to check if a given element exists in the list.

---

## 🧠 Algorithm

1. **Step 1:** Define a class `Nodeq` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   - `prev` to store the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `head` to point to the first node.

3. **Step 3:** In the `DoublyLinkedList` class, define methods:
   - `insert_beginning(data)` to insert a node at the beginning.
   - `insert_end(data)` to insert a node at the end.
   - `search(data)` to search for an element in the list.

4. **Step 4:** Create an instance of `DoublyLinkedList`.
   - Insert elements at the beginning and end.
   - Search for specific elements.

---

## 💻Program

```python
class Nodeq:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None

    def insert_beginning(self, data):
        new_node = Nodeq(data)
        new_node.next = self.head

        if self.head:
            self.head.prev = new_node

        self.head = new_node

    def insert_end(self, data):
        new_node = Nodeq(data)

        if self.head is None:
            self.head = new_node
            return

        temp = self.head
        while temp.next:
            temp = temp.next

        temp.next = new_node
        new_node.prev = temp

    def search(self, data):
        temp = self.head

        while temp:
            if temp.data == data:
                return True
            temp = temp.next

        return False

dll = DoublyLinkedList()

dll.insert_beginning(20)
dll.insert_beginning(10)
dll.insert_end(30)
dll.insert_end(40)

if dll.search(30):
    print("Element found")
else:
    print("Element not found")
```

## Output

```text
Element found
```

## Result

Thus, the Python program was successfully executed to search an element in a Doubly Linked List.

