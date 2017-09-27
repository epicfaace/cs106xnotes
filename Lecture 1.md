# Include
- ```#include <c++systemlibrary>```
- ```#include "localprojectlibrary.h"```

# Namespaces
- ```using namespace std;``` (```cout``` is in this namespace; full name is ```std::cout```)

# Hello world
~~~~
int main() {
    cout << "Hello " << "world!" << endl;
    return 0;
}
~~~~

# Include console.h -- its own window (Stanford's library)
Always include this:
~~~~
#include "console.h"
~~~~

# Cin
- ``` cin >> abc```
- this is discouraged! No type checking.

~~~~
int age;
cout << "what is your age?";
cin >> age;
cout << "Age is " << age;
return 0;
~~~~

- initializing variables: unset variables are set to garbage, not just 0.

# Use simpio instead
~~~~
#include "simpio.h"
getInteger("prompt")
getLine("prompt")
getReal("asdasd") -- floating point
getYesOrNo("asdsad") - y/n
~~~~