## Divs
I would recommend putting each element/group of elements you want to arrange and format inside a `<div class="classname">` tag

## Sizing Elements
`width` - the width of the element
`height` - the height of the element

#### Units
`1px` - pixels
`1fr` - fraction of the screen (used to create equal sized things)
`1em` - relative to the size of the current font - ie. `1em` is one letter space etc.

## Element Types
**Block level element** - These elements will take up a chunk of page the size of the block. You will not be able to put anything next to them. By default `<div>` elements are block level elements.

#### Float
**Float level element** - Positions an element to the left or right side of the container. Allowing elements to wrap around it and to be on the same line as it. 
`float: {left/right}` - makes an element a float level element and sets the side.
`clear: {left/right/both}` - stops an element from floating. Used if you want 3 boxes next to each other but then don't want the text underneath to be next to the boxes - you want it to be on the next line.

## Margins
**The space around an element**
`margin: 50px;` - sets a 50 pixel margin on all 4 sides of the box
`margin-right: auto;` - set right margin to automatic - will keep the box on the left of the screen
`margin-left: auto;` - set left margin to automatic - will keep the box on the right of the screen
_Setting both of these to auto will centre the box in the screen_

## Positioning Elements
For the `position` tag, there are 5 main different options:
#### Static
`position: static;`
The default option

#### Relative
`position: relative;`
Moves itself based off of a point of origin. The default point of origin is the top left corner of where it initially sat (probably the bottom left corner of the previous element). 
You can then set properties like `top` and `left` to move it relative to that position a certain number of pixels. 
This will cover other elements if comes into contact and will also reserve the original space of the box so no elements can go there.

#### Absolute
`position: absolute;`
Taken out of the flow of the document - elements after it will go underneath it.
The positioning is done relative to any 'parents' it has that are positioned non-statically, ie. not with the default option. Options like `top` and `left` can again be used to move the box around.

#### Fixed
`position: fixed;`
Stays in set position on the view port (window) - doesn't move from where it is if you scroll. An example would be some nav bars that always stay at the top of your screen on some websites.

#### Sticky
`postition: sticky;`
Stays in its initial position until you scroll past it, then it will stick to that edge of your screen.
Setting a property like `top` will make it stick that many pixels away from the top of your screen when you scroll past.