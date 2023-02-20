## Fonts
`color` - Change font colour
`font-family` - change text font (can have multiple fonts for if web browser does not support previous fonts)
`font-style` - set things like itallic
`font-weight` - set bold and how bold
`text-decoration` - set underline and other underline settings
`font-size` - change font size

## Shadows
`text-shadow: 5px 5px 5px blue;`
`box-shadow: 5px 5px 5px blue;`
First number is for the X offset, if the number is negative it will go left.
Second number is for the Y offset, if the number is negative it will go up.
Last number is for the strength/spread of the shadow. A higher number results in a more faded shadow.
Multiple shadows can be added to the same piece of text using comma separated shadows:
`text-shadow: 5px 5px 5px blue, 0px 0px 5px green;`

## Borders
`border-style` - what the border looks like
`border-width` - width of border in pixels
`border-color` - border colour
`border-radius` - round corners
`padding` - space between text and border

Can specify which border side you wish to change using `border-{side}-{attribute}` using top, bottom, left, right as the sides and all the attributes listed above as the attributes

## Background
`background-color` - set background colour
`background: linear-gradient(to {side}, color1, color2);` - set a background gradient. It will end at the side chosen
`background-repeat: no-repeat;` - prevent background from repeating every block
`background-attatchment: fixed;` - means the background will stretch the whole page no matter the size

#### Images
`background-image: url("background.jpg");` - set an image as the background. An external URL can also be used
`background-position: center;` - have the image centred on the window
`background-size: cover;` - have the image resize to cover the whole window
_Would also recommend using `background-repeat` and `background-attatchment` attributes with a photo_

**Backgrounds can be set to individual HTML elements not just the whole body**

## Pseudo Classes
These are kinda like states of an element, like a button being hovered or clicked.
You can then apply any CSS attributes you wish to the element if it enters that state.
#### States
- `:link`
- `:visited` - for a link
- `:hover`
- `:active` - when it is currently being clicked on
**nth-child**
`li:nth-child()`
This is used to apply CSS attributes to element `n` or every `n` elements.
Doesn't have to be use on `li` but that is just an example.
`:nth-child(1)` - the first child
`:nth-child(even)` - every other element (even ones). Can also be `odd` and can use both to alternate between the elements
`:nth-child(3n)` - every 3 elements. Can be set to whatever number you wish
`:nth-child(4n+1)` - every 4 elements STARTING at element 1. Or whatever starting element you wish.

