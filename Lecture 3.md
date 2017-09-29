Friday 9/29/2017
## Strings
~~~~
#include <string>
...
string s = "hello";
char c1 = s[0]; // 'h'
char c2 = s.at(0); // 'h'
~~~~
- Two types of strings in C++!
- Characters
- ASCII encodings: `cout << (int) s[0] << endl; //72`
- Concatenate strings with +
- Compare with relatioanal operators (Use < or > for ASCII ordering, use == and != to compare strings)
- Strings are **mutable** and can be changed (!).
~~~~
- s1.append(" Stepp"); //modifies the s1 string! doesn't return a new object.
~~~~
- `s.find(str)` -- returns `string::npos` if not found.
# Stanford string library
~~~~
#include "strlib.h"
endsWith(str, suffix), etc.
integerToString, etc.
trim(str), etc.
~~~~

## String user input
`cin` only reads one word at a time.
Stanford library `string name = getLine("Type your name: ");`

## Two types of strings: C and C++ strings
- C strings = char arrays. C++ strings = `string` objects.
- "abc" is a C string. string("") is a C++ string.
- `string s = "hi" + "there"; ` - C string + C string. wrong.
- `string s = string("hi") + there; ` - C++ plus C. correct.
 

# I/O Streams & Grids
Read files (i) and write (o)
## Read files - ifstream.
~~~~
#include <fstream>
// classes ifstream, ofstream for input/output files.
f.open("filename.txt");
f >> var //reads one whitespace-sep token at a time
getline(f&, s&);
~~~~
Example:
~~~~
ifstream input;
input.open("poem.txt");
string line;
while (getline(input, line)) {
    cout << line << endl;
}
input.close();
f.close();
~~~~
## Operator >>
~~~~
string word;
input >> word; "Marty"
input >> word; // "is"
input >> word; // false when last word.
~~~~

## istringstream
What if I want to tokenize a string? `istringstream` to the rescue!
~~~~
#include <sstream>
istringstream input("A b c");
string first, second, third;
input >> first >> second >> third; //first = "A", second = "b", third = "c"
~~~~

## ostringstream
Works just like strout, but just outputs to a string (like a StringBuilder).
~~~~
#include <sstream>
ostringstream output;
output << "ABC" << "DEF" << endl;
output << "ASDASD" << endl;
string result = output.str();
~~~~

## Stanford stream library
~~~~
#include "filelib.h"
deleteFile(...)
readEntireFile(...)
etc.
~~~~

# Collections: Grid
- **collection** - stores data.
- standard template library (STL) - built in standard library of collections. (vector, map, list, etc.)
- SPL - stanford C++ library collections.
~~~~
#include "grid.h"
// like a 2D array.
//constructing a grid
Grid<int> matrix(3, 4); //3 rows, 4 cols
matrix[0][0] = 75;
//or specify all elements as:
Grid<int> matrix = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12}
};
g.numRows(), g.numCols()
g.resize(nRows, nCols);
g.toString()
~~~~
- pass a grid by reference (ampersand), otherwise it will make a _copy_ of the contents!
- add `const` to the parameter name too!