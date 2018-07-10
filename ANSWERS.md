## _Why does  `FixedArrayQueue`  require an explicit constructor?_
Unlike the book's implementation of a queue, `FixedArrayQueue` does not have a default capacity and is not expandable. Instead, the capacity is determined by the user when the `FixedArrayQueue` object is created. Thus, we need an explicit constructor where capacity is an argument to create the correctly sized queue.
## _What happens when you offer an item to a full  `FixedArrayQueue`?_
Since this implementation of a queue has a fixed size, the item is rejected and `false` is returned to the method call.
## _What happens when you poll an empty  `FixedArrayQueue`?_
If there are no items present in the queue when `poll()` is called, the method will return a null value.
## _What is the time and (extra) space complexity of each of the  `FixedArrayQueue`  methods?_
The time complexity for all of the `FixedArrayQueue` methods except `asList` are O(1) because `front` and `rear` are not static based on capacity, rather they are reassigned as elements are added/removed. Because of this, all of the array elements are not required to shift each time an element is added or removed, therefore the operations perform in constant time.

The time complexity for `asList` is O(n) as the method must iterate through the entire queue to add it to a list. The time it would take to complete this operation will increase as the size of the queue increases.

The space complexity for all `FixedArrayQueue` methods except `asList` are O(1) as they declare no variables that require N amount of space. The space complexity for `asList` is O(n) as it creates a new `ArrayList` of size N.


