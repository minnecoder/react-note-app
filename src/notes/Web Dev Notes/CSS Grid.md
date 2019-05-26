# CSS Grid Notes
Reference can be found at https://css-tricks.com/snippets/css/complete-guide-grid/

To make CSS grid work the below CSS needs to be in place whether it’s in a style tag or in a seperate CSS file.
``` css
.container {
	display: grid;
}
```
`grid-gap: Xpx ;` - adds a gap to each item with the specified size
`grid-template-columns: XXpx auto;` - tells the browser how many columns there will be and the size of each.
* the keyboard shortcut for  `grid-template-columns` is type `gtc` and hit the `tab` key

`grid-template-rows: XXpx auto;` - tells the browser how many rows there will be and the size of each
* with either of the grid-template options there is the use of `fr` units. These are useful when there is a need to size the columns or row evenly on the page
* using the `auto` option will set that column or row to the object that has the biggest size. 
* When using `grid-template-rows` the height has to be set before elements will be able to go all the down to the bottom of the screen.

When using `grid-template-columns` and there is a need to have the widths of columns repeating, use `repeat` the following syntax is used  `grid-template-columns: repeat(<number of times to repeat>, <what to repeat>);` 

* `auto-fill` - fills each row with as many columns that are able to fit  i.e. `grid-template-columns: repeat(auto-fill,150px);`
* `auto-fit` - fits the currently allowed number of columns into each row  i.e. `grid-template-columns: repeat(auto-fit,150px);`

### Explicit vs. Implicit

Explicit is the columns and rows that are set by the use of `grid-template-columns` and `grid-template-rows`. Items that fall outside of the explicit area are implicit items. 

Implicit items can be set through the use of `grid-auto-rows` using the syntax of `grid-auto-rows: XXpx;`

A grid can be 100% implicit. If there is only need for one column, there is no need to define the size of the columns. Only the size of rows would need to be defined.

### Sizing Items

To make a website responsive while using CSS grid and repeat, `minmax()` can be used. Within the parenthesis, the minimum size and the maximum size need to be entered i.e. `grid-template-columns: repeat(auto-fit,minmax(150px, 1fr));`. The preferred size for the maximum size is `1fr` 

`grid-auto-flow: row;` - is the default option and won't do anything different than what would normally happen. 
`grid-auto-flow: column;` - this will create a new column for each item that is added to a grid. 
`grid-auto-columns: XXXpx;` - sets the width of any columns that are implicitly created to the specified width. 
`grid-column: span X;` - allows the item that this is called on to take up the space of 2 columns within CSS grid
`grid-row: span X;` - allows the item that this is called on to take up the space of 2 rows within CSS grid
* `grid-row: span` and `grid-column: span` can both be applied to the same item if it is needed. 

`grid-column-start:2` - starts  a column at "track 2"
`grid-column-end:5` - ends  a column at "track 5"
* the shorthand version of the above commands are `grid-column: 2 / 5;`
* setting the second number in `grid-column` to `-1` will select the whole row. i.e. `grid-column: 1/ -1;`



### Item Placement

In the case that there is an item that leaves empty spaces on a row, `grid-auto-flow: dense` can be used. This will take the next item(s) to fill up the empty spaces.





### Grid Template Areas
In order to name sections of the grid, it is done by first using `grid-template-area:` and below this is a line for each row that has what section each column will belong to. 

For example for a grid that has 3 columns and 3 rows, with sidebars on the left and right of a content section and a footer along the bottom. The lines for this would look like this:
```css
grid-template-areas:
	"sidebar-1 content sidebar-2"
	"sidebar-1 content sidebar-2"
	"footer footer footer"
```
To exclude a column in a row from a section, a period would be typed in that space.

To place something inside of a template area, the following code would be used:
```css
.item1 {
	grid-area: sidebar-1;
}
```
When templates are used along with media queries, there is the ability to change the layout of the template area so that things are easier to view on the smaller screen size. An example of how this would look is below: 
```css
@media (max-width: 700px) {
	.container {
		grid-template-areas:
			"content content content"
			"sidebar-1 sidebar-1 sidebar-2"
			"footer footer footer"
	}
}
```

### Naming Lines in CSS Grid
To name lines in CSS grid, these names are placed in square brackets where the lines are needed i.e. 
`grid-template-columns: [site-left] 1fr [content-start] 500px [content-end] 1fr [site-right];`

After this is setup, the start and ends of columns and rows can be set to one of these named sections i.e.
```css
grid-column: content-start;
grid-row: content-top / content-bottom;
```

If there are empty spots in the grid because of different sizes of rows, `grid-auto-flow: dense;` will fill those empty spaces with items that can fit those spaces.


### Alignment and Centering
Justify objects are for rows or things on the x-axis and align is for columns or things on the y-axis.
#### Align/Justify Items

* Aligns the elements that exist within a given item

The default of `justify-items` is stretch. 
`justify-items:center` will center each item and make it as small as needed. 
`justify-items:start` - will move all of the item contents to the left side
`justify-items:end` - will move all of the item contents to the right side

`align-items: center;` - will center the content
`align-items: start;` - will move the content to the top
`align-items: end;` - will move the content to the bottom
* There is a shorthand version for both align and justify and that is `place-items`. The syntax for this is `place-items: center center`. This is only supported in Chrome and Firefox. 
#### Align / Justify Content
* These options are used when the grid does not take up the whole size of the web page.
* This is used to move the grid items  within the grid area

`justify-content: start` - all of the grid items will be moved to the left side of the screen
`justify-content: center` - all of the grid items will be moved to the center of the screen
`justify-content: end` - all of the grid items will be moved to the right side of the screen
`justify-content: stretch` - all of the grid items will be stretched so that all of the grid items will fill the screen.
`justify-content: space-around` - all of the grid items will have extra space on both sides of each item so that they will fill the screen.
`justify-content: space-between` - all of the grid items, except for the first and last items, will have extra space on both sides of each item so that they will fill the screen.

`align-content: start` - all of the grid items will be moved to the top of the screen
`align-content: center` - all of the grid items will be moved to the center of the screen
`align-content: end` - all of the grid items will be moved to the bottom of the screen
`align-content: stretch` - all of the grid items will be stretched so that all of the grid items will fill the screen.
`align-content: space-around` - all of the grid items will have extra space on both sides of each item so that they will fill the screen. (Items on the edge will have less space between the edge of the grid area and the outer items)
`align-content: space-between` - will place the outer items to the left and right edge of the grid area and space the interior items accordingly

#### Align/Justify Self
`align-self` and `justify-self` are used on each element that needs to have changes made to the content of that element.

`justify-self: start` - the grid items will be moved to the left side of the element
`justify-self: center` - the grid item will be moved to the center of the element
`justify-self: end` -  the grid item will be moved to the right side of the element
`justify-self: stretch` - the grid item will be stretched so that all of the grid items will fill the element

`align-self: start` - the grid item will be moved to the top of the element
`align-self: center` - the grid item will be moved to the center of the element
`align-self: end` - the grid item will be moved to the bottom of the element
`align-self: stretch` - all of the grid item will be stretched so that all of the grid items will fill the element

