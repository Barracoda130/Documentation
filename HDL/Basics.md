## Setup
A logic gate created in HDL is created using 2 parts - the _header_ and the _parts_.

## Chip definition
```HDL
CHIP Xor {
	// Header
	IN a, b;
	OUT out;
	
	// Parts
	PARTS:
	And (a=a, b=b, out=x);
	OR (a=a, b=b, out=y);
	NOT (in=x, out=notx);
	And (a=y, b=notx, out=out);
}

```

```hdl
CHOP Foo {
	In in[8];
	OUT out[8];

	
}
```

Overlap of inputs/outputs is OK.
Chip names and file names should be the same. Only make one chip per file.

## Script Testing
Script files end in `.tst`
```tst
load CW1.hdl,
output-file CW1.out,
output-list a b c f;

set a 1, set b 1, set c 1, eval, output;
set a 0, set b 0, set c 1, eval, output;
set a 1, set b 0, set c 1, eval, output;
```
Final line of the file ends in `;`, all other lines end in `,` 