10/6/2017

# Set

***set*** - a collection of unique values
- give up indexes, insertion order.
- can efficiently perform: add, remove, search.
- ex: word count exercise. *Slow to check if a vector contains something.*
~~~~
#include "set.h"
Set s;
s.add(value);
set.contains("to")
~~~~

## Two kinds of sets in C++
- Set: implemented using a binary tree.
  - elemtns stored in sorted order (used in a foreach loop); elements must have a < operation.
- HashSet - implemented using a hash table ```include hashset.h```
  - unpredictable order
  - values must have a ```hashCode``` function.

## Set operators
==, != +, +=, * (intersection), *= (set left to intersection), -, -=

## Looping over a set using ```foreach```:
~~~~
for (int i : s) {
    statements; 
}
for (int i = 0; i < set.size(); i++) // doesn't work!!! no indexes for set.
~~~~

# Structs
- Like a lightweight class; usually just stores data.
- by default, member variables and methods are public.
~~~~
struct Date {
    int month;
    int day;
}
Date today;
today.month = 7;
today.day = 13;
Date xmas {12, 25}; // initialize on one line.
~~~~

# Operator OVERLOAD!
~~~~
bool operator <(const Date& d1, const Date& d2) {
    return (d1.month < d2.month) || (d1.month == d2.month && d1.day < d2.day);
}
~~~~

# Stanford lexicon
- optimized for dictionary and prefix lookups.
~~~~
#include "lexicon.h"
Lexicon l;
l.add(word);
l.contains("word");
l.containsPrefix("str");
~~~~

# Maps
- stores a key and a value. "dictionary", "assoc. array", "hash"
~~~~
#include "map.h"
Map<string, int> m;
m.put(key, value); or m[key] = value;
m.get(key); or m[key]
m.remove(key);
~~~~
## C++ -- two map classes
- Map: binary search tree. sorted order. < fn.
- HashMap: hash table. unpredictable order. hashCode fn.
- Loop over a map! You'll get the key.
- ```for (string key : m) { ... m[key] ... }```

## Maps and tallying
- "RDDDDDIIRRR"
- ```map.containsKey("key")```