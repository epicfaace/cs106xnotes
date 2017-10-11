10/9/2017

    +---------------
    |
    | What is recursive programming?
    | 
    | Writing a function that calls itself.
    | Works well with problems that are "self-similar".
    | 
    | factorial(N)
    | 
Recursion. base case and recursive case. Good for reversing things.

10/11/2017
# File lib
~~~~
#include "filelib.h"
function crawl(filename, string indentation="") {
    cout << indentation << getTail(filename) << endl;
    if (isFile(filename)) {
        // b.c.
    } else {
        // r.c. - directory.
        Vector<string> files = listDirectory("fileName");
        for (string file: files) {
            crawl(filename + "/" + file, indentation + "    ");
        }
    }
}
~~~~

# Memoization: Reuse
- Fib call tree -- fib(6) = fib(5) + fib(4) -- repeats fib(4) twice!
- ***memoization***: caching reults of previous expensive function calls for speed so that they do not need to be re-computed.
- Store results in a cache.
~~~~
int fib(int n) {
    static HashMap<int, int> cache; // this is function-private data. created the first time the function is called. NO GLOBALS!
    if (n <= 2) {
        return 1;
    } else if (cache.containsKey(n)) {
        return cache.get(n);
    } else {
        int result = fib(n-1) + fib(n-2);
        cache.put(n, result);
        return result;
    }
}
~~~~