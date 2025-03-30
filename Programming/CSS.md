Learn the box model

think of every CSS element as a box. inside that box there's the content

every box has a width and height
	you can have padding around the box to squeeze the content
	you can have a border
	you can have an invisible space outside the border called the margin

open dev tools in chrome to see the how the box model is computed for every element on the page
	use firefox dev tools to debug CSS
	you can change values directly
	you can also see the properties that influence the box model
	flex and grid layout

Layout is the positioning of things relative to each other is the most challenging aspect of CSS

Flexbox
	allows you to create a flexible column or row anywhere on the UI
	it has a x and  y axis on which you can align its children
	the children flow one way called the main axis
	**justify-content: center** to align the content in the center
	The cross axis is perpendicular to that
	**align-items: center** to align the properties in the center in the other axis
	
containers and wrappers?

Grid
	you can set an element to display grid you can then define its children as columns and rows
	columns have a width which can be defined with the grid template columns property
		grid-template-columns: 1fr 500px 1fr
	we have three columns
		fr = fractional unit, it divides equally the space of the page
	rows
		grid-template-rows: 100px 200px 100px
	we now have three rows

responsive layout
	basically changing the width of something based on the device
	use clamp, min and max

clamp
	article {
		width: clamp(200px,50%,600px);
		}
	they are respectively min preferred and max

there is an aspect ratio function in CSS
	aspect-ratio: 16/9;

custom properties and values
	in the root selector create a variable
		:root  {
			--text-color: red
		}
		you can use them using var(--text-color)
	you can reference it everywhere
	you can also redefine them lower in the code
	you can also use variable composition
		--r: 255;
		--g: 0;
		--b: 0;
		--text-color: rgb(var(--r),var(--rg),var(--b),

Calc function
	it allows you to do basic calculations

you can have counters in CSS
	root: {
		counter-reset: headings;
		}
	h1: {
		counter-increment: headings;
		} 
	h1::before {
		content: counter(headings);
		}

focus class and focus within class, which stays active when its children are in focus

i don't understand these two last things

browser prefixes?
	check out postCSS adds all the prefixes automatically and lets you use modern CSS features on the targeted browser even if they are not supported

Preprocessors?
	sass
	stylus
	less

Use relative units like em and rem
	em calculates the size automatically based on the font size of its nearest parent
	rem is relative to the root font size
	there are more relative units than em and rem
		ch for character width

"elements of typographic style" the optimal size for a paragraph is from 45 to 75 characters

clamp (45ch , 50%, 75ch)

use hsl colors instead of rgb or hex, click on the top of the color to change its representation

create a color pallette quickly by choosing a color and changing the hue by a certain amount every time

navbar covers the anchor text? use scroll padding property



