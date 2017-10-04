# Stacks and Queues
Wed 10/4/2017
***stack*** - add/remove from "top" only.
***queue*** - add to "back" only; remove from "front" only.

## Stacks
- LIFO - last in, first out. Like a stack of books.
- elements are stored in order of insertion; don't think of it as having indexes.
  - one can only add/remove/view the top element (last added).
- push - add element to top
- pop - remove top element
- peek - examine the top element
Use: "undo stack", backtracking, forward / reverse, functions/compilers use stacks.

### Stack class
~~~~
#include "stack.h"
Stack<int> s
s.isEmpty()
s.peek()
s.pop()
s.push(value);
s.size()
~~~~
### What you can't do with stacks
- You ***cannot*** access a stack's elements by index. Common idiom: pop each element until stack is empty.

- Stacks - O(1) for all operations!
- Implemented using an array / vector internally. 'bottom" = index 0, top = index (size - 1). Or implemented using a linked list.

# Queues
- FIFO - first in, first out. Like joining the end of a line.
- Example: print job queue, queue of network packets, waiting in line, etc.
~~~~
#include "queue.h"
Queue<int> q;
q.dequeue()
q.enqueue(value)
q.isEmpty()
q.peek()
q.size()
~~~~
- Implementation: linked list, or circular array.
- All ops are in constant time.
- Idioms: loop through elements by dequeueing them, then re-adding them to the queue.
- 
- To reverse order of a queue, use a stack.

# Deque
- double-ended queue. can add or remove. ```#include "deque.h"```