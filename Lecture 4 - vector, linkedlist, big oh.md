Monday 10/2/2017
# Vector, LinkedList, Big-O notation
## Vector (list)
- a collection of elements
  - like a dynamically resized array. (`ArrayList` from java)
~~~~
#include "vector.h"
Vector<int> nums {1,2,3,4,5};
Vector<string> names;
names.add("Stu");
names.insert(0, "Ed");
.remove(i);
.size()
//actual arrays in C++ are mostly awful
~~~~
### Iterating with loops:
~~~~
for (string name: names) {
cout << name << endl;
}
for (string& name : names) { //for-each by reference.
~~~~
### Insert / remove
~~~~
v.insert(2, 42); // shift elements right to make room for new element, 42.
v.remove(1); // delete element 1 and slide elements left.
~~~~
So, it's slower when you insert/remove elements closer to the front.
Backwards foreach loop -- if you want to remove some elements.
### Nested vectors
~~~~
Vector <Vector<int> > vv;
vv.add({1, 2, 3});
vv[0][0] // 1
~~~~

# Vector Implementation and Big-Oh Notation
- A vector has an array inside, and stores **size** and **capacity.**
  - Array is slightly larger than data (so room to add elements) -- unfilled space.
- **Insert** shift elements right, increment size.
  - Insert/remove at the front is slow. -- runtime related to size of vector (number of elements to shift).
## Efficiency
**Efficiency** -- can be speed (runtime), memory, etc.
- Single statement's runtime = 1
- Function call runtime = sum of runtime statements in body.
- Loop of N iterations' runtime = N * (loop body's runtime).
- Nested loop (n times inside n times) = n^2
- 0.4N^3 + 25N^2 = O(N^3). **big O**
### Efficiency of vector operations
v.add(a), v.get(i) - O(1) = constant (not related to N)
v.insert(i, value) or v.remove(i) - O(N) (average-case runtime).
v.toString() - O(N)