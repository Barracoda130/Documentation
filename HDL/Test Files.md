## Output list
```tst
output-list time%S1.4.1 x%D%1.6.1 out%D1.6.1;
```
`%S` and `%D` are saying make it either a string or a digit.
`1.6.1` - 1 space before, then 6 digits, then 1 space after. If the thing it is outputting isn't 6 digits then it will pad with spaces.

## Running the Program
`tick, tock` - 1 clock cycle
`set x 0` - sets input X to 0. If you don't change that then it will keep the same input value for  the next output
`output;` - write to the output file
