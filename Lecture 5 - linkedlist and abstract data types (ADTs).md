Wed 10/4/2017
**LinkedList** has the same functionality as ```Vector```.
~~~~
LinkedList<int> list;
list.add(1);
~~~~
- Made of nodes, each stores a value and pointer to the "next" node.
- List knows only its ***front*** node.
- Inserting in linked list: no "shifting", but need to add a new node.
- 
***Abstract data types*** - collection of data and operations that can be performed on it. For example, both ```Vector``` and ```LinkedList``` implement the abstract data type called "list".

When is linked list faster than vector? -- inserting at beginning.