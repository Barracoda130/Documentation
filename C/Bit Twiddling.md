## Left shift
```C
// 14 is stored as 0000 1110
unsigned char myNumber = 14;

// shift it left by 2 bits
myNumber <<= 2;

// now holds 0011 1000
// Multiplies by 2^2 or 2^shift-size
```

## Right shift
Only do when unsigned
```C
// 14 is stored as 0000 1110
unsigned char myNumber = 14;

// shift it left by 2 bits
myNumber >>= 2;

// now holds 0000 0011
// Divides by 2^2 or 2^shift-size
```

## Bit Masks
Work like a stencil

#### Writing Bits
1. Compute bit mask
2. Take its inverse

`~` - bitwise NOT

## SWAP
```C
#define SWAP(X, Y) { (X) ^= (Y); (X) ^= (Y); (X) ^= (Y);}
```