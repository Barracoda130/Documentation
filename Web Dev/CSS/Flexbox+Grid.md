## Flexbox
Used to layout elements that want to be arranged horizontally of varying width that will change depending on the width of the content of the element.

Create a class called something like "flex" and this can then be used to set generic flexbox elements.
To make something a flexbox type `display: flex;`

#### Useful commands
`flex-wrap: wrap;` - means that if the flexbox hits the edge of the screen and can't squeeze anymore, it will wrap to the next line
`flex-direction: row;` - the default direction for the flexboxes to go
`gap: 1em`

**Flex only allows you to do very limited layout changes at the higher levels, all commands below here will need to be done inside `.flex > * {` ie. all the children of the flex class**
`flex-grow: 1;` - sets the columns to all the same size
`flex-basis: 33%;` - sets default of 3 columns (33% of the screen)



## Grid
Used to layout elements that want to be arranged in a consistent size in a 2D grid like pattern.

Create a class called something like "grid" and this can then be used to set generic grid elements.
To make something a flexbox type `display: grid;`

#### Useful commands
`grid-template-columns: 1fr 1fr 1fr;` - makes the grid display columns rather than just rows, and this will make 3 columns using the `fr` (fraction) unit.
`grid-template-columns: repeat(autofit, minmax(300px, 1fr));` - makes it look a bit like flexbox however all columns will be the same width. It also sets min and max values for this.