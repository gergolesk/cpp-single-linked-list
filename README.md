# **Singly linked list**
*Yandex.Practicum educational project*

A singly linked list is also called a linear singly directed list. This data structure consists of elements of the same type. They are logically linked together by pointers. Each list element points to the next one, and the last one points to nullptr. List elements are usually stored in dynamic memory.

The structure of a singly linked list is such that you can only move along its elements in a forward direction. It is impossible to find out the address of the previous element based only on the contents of the current element.

**A singly linked list allows the following operations:**
- inserting an element at the beginning or end of the list,
- inserting an element after a certain list element,
- deleting an element following a given list element,
- checking if the list is empty,
- determining the number of elements in the list.

**Advantages of a singly linked list:**

insertion and deletion of an element are performed in constant time, that is, they do not depend on the number of elements and the position of the element being inserted or deleted;
the list size is limited only by the amount of available memory.

**The disadvantages of a singly linked list follow from the features of its structure:**

Finding the address of an element by its serial number is a linear complexity operation. To determine the address of the N-th element of the list, you need to sequentially iterate over all N-1 elements, starting with the first element.
Inefficient memory usage: in addition to data, each element of the list stores a pointer to the next element. In addition, each time an object is created in dynamic memory, a couple of dozen bytes are spent on maintaining the heap structure.
Not such high efficiency of insertion and deletion. Each insertion and each deletion accesses heap operations: new or delete. These operations are considered to work in constant time, but the constant can be quite large. In this case, complex synchronization code between threads is executed, and low-level mechanisms for working with memory can be involved.
Neighboring elements of the list can be located in memory out of sequence, which reduces the efficiency of the cache memory.

The list class supports iterating over the elements of the SingleLinkedList container using the BasicIterator template class, which is used to declare constant and non-constant list iterators.
The list class also implements constant and non-constant versions of the begin and end methods, which return iterators to the first element of the container and the position following the last element. To make it convenient to obtain constant iterators, the cbegin and cend methods are implemented.

**The following functionality is implemented in the singly linked list class:**
- Comparison operations ==, !=, <, >, <=, >=;
- Exchanging the contents of two lists using the swap method and the swap template function;
- Constructing a singly linked list based on initializer_list. The sequence of elements in the created list and initializer_list is the same;
- Reliable copy constructor and assignment operator. The assignment operator provides a strong exception safety guarantee. If an exception is thrown during the assignment, the contents of the left argument of the assignment operation remain unchanged.
- The PushFront method provides a strong exception safety guarantee: if an exception is thrown during the method's execution, the state of the list will remain the same as before the method was called.
- The Clear method clears the list and does not throw exceptions.
- The PopFront method. Removes the first element of a non-empty list in O(1) time. Does not throw exceptions.
- The InsertAfter method. Inserts a new value into the list in O(1) time following the element referenced by the iterator passed to InsertAfter. The method provides a strong exception safety guarantee.
- The EraseAfter method. Removes from the list the element following the element referenced by the iterator passed to InsertAfter in O(1) time. Does not throw exceptions.
- The before_begin and cbefore_begin methods. Return iterators that reference a dummy position before the first element of the list. Such an iterator is used as a parameter for the InsertAfter and EraseAfter methods when you need to insert or remove an element at the beginning of the list.

## Build and install
Build using any IDE or build from the command line

## System requirements
C++ compiler with support for the C++17 standard or later
