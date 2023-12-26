## Algorithms
#### Replace
```c++
// Replace all 0s with 1s
vector<int> v;
replace(v.begin(), v.end(), 0, 1);

// Replace negative values with 0
replace_if(v.begin(), v.end(), is_negative, 0);
```

#### Count
```c++
// Count all negative values
vector<int> v;
int n = count_if(v.begin, v.end, is_negative);
```

## Operator Overloading
Operators like `+` can be overridden in C++. You can specify what is on the LHS and RHS and change what the operator does based off of that.
```C++
// NOT INSIDE CLASS
Money operator+(const Money& m1, const Money& m2)
{
    int e = m1.getEuros() + m2.getEuros();
    int c = m1.getCents() + m2.getCents();
    return Money(e + c / 100, c % 100);
}
```
These overloaders CANNOT be defined as part of the class, they must be defined outside!