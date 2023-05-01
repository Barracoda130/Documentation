## Dynamic Storage Allocation
Create an array of floats called data of size `size`.
```C++
float *data = new float[size];
delete[] data;
```
In C++ `new` replaces `malloc()` and `delete` replaces `free()`.

## Vectors
```C++
#include <vector>
using namespaces std;

vector<int> a;               // empty vector for ints
vector<int> b(10);           // empty vector for ints
vector<int> c(5, -1);        // empty vector for ints
vector<int> d(c);            // empty vector for ints

vector<string> p;            // empty vector for ints
vector<string> q(5, "xyz");  // empty vector for ints
```

#### Adding and Removing
`.push_baack("thing")` - put thing at the end of the vector
`.size()` - size of thing
`.pop_back()` - removes last item and returns it
`.clear()` - empties vector

## Algorithms
`v` is an already defined vector, and `is_negative` is a function we wrote that returns a bool.
`.replace(v.begin(), v.end(), 0, 1)`
`.count_if(v.begin(), v.end(), is_negative)`
`.replace_if(v.begin(), v.end(), is_negative, 0)`