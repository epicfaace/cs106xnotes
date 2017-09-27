9/27/2017
Topic: **functions and strings.**
- defining a function
- default parameters
~~~~
void printLine(int width=10, char letter = '*') {...}
~~~~
# declaration order.
Function declared at top of file, so compiler is okay.
~~~
double circleArea(double radius);
~~~
If default parameter, default goes only in prototype, and not in actual function body code below.

# Math functions
(in the std namespace)
~~~
#include <cmath>
abs(value), etc.
~~~

# Semantics
## Value semantics
- when variables (int, double) are passed as parameters, their values are copied. i.e., it doesn't affect the initial parameters.
## Reference semantics
Object **reference.**
~~~
void swap(int& a, int& b) {
    a = b;
}
int x = 1;
int y = 2;
swap(1, 2);
// x = 2, y = 2.
~~~
## Output parameters
~~~
void datingRange(int age, int& min, int& max) {...}
int main() {
    int young, old;
    datingRange(48, young, old);
    // now young and old will be set.
...
}
~~~
- sometimes make an object reference for efficiency (otherwise it will copy the entire object passed)

## Downsides of reference parameters:
- can't tell if foo changes a b or c
- slightly slower for objs
- can't pass a literal value; must pass in a variable (not ```grow(39)``` but ```grow(age)``` )

