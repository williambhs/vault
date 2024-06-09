Flexbox, short for flexible box layout - provides an efficient way to align items among containers

To use - usually you want to create a container class, then to enable flexbox do:
display: flex;
To convert the element into a flex container.

Two axis' - main axis, and cross axis
The main axis is defined by flex-direction and determines the direction of the flex items
Cross axis is perpendicular to the main axis and is used for alignment

Once the element has been converted into a flex container, here are some useful properties for containers:

-----


**flex-direction** - defines the direction of the main axis. 

**flex-direction: row;**
The default way elements are styled.

+-------------------------------------------+
| Item 1 | Item 2 | Item 3 | Item 4 | Item 5 |
+-------------------------------------------+

**flex-direction: row-reverse;**
The same thing, just laid out from right to left.

+-------------------------------------------+
| Item 5 | Item 4 | Item 3 | Item 2 | Item 1 |
+-------------------------------------------+

**flex direction: column;**
Items are stacked vertically from top to bottom.
+--------+
| Item 1 |
+--------+
| Item 2 |
+--------+ 
| Item 3 | 
+--------+ 
| Item 4 |
+--------+
| Item 5 | 
+--------+

**flex direction: column-reverse;**
not going to include a visual because... obvious reasons.

**justify-content**
aligns flex items along the main axis - 

**justify-content: flex-start;**
the default - items are packed towards the start of the main axis

**flex-end** - does the opposite
**center** - items are centered along the main axis
**space-between** - items evenly distributed with the first item at the start and last at the end
**space-around** - items evenly distributed with equal space around them
**space-evenly** - items are evenly distributed with equal space between them 
Important distinction between space-around and space-evenly:
space-evenly makes equal space around all items and edges. Each gap between items and container edges is identical.
space-around also makes equal space around items, but edge spaces are half the size of spaces between items - that means there's more space between the item and container edges vs space between items. To be exact, the space between items is 2x as much as the space between the items and the containers edges. For example, if a container has a margin of 50px between the containers edges and the items, the space between the items will be 50x * 2 or 100px for space-around, but 50px all around for space-evenly.

Thus, space-around should be used when you want to emphasize the separation between items while keep them close to the edges of the containers edges whereas space-evenly should be used if you want equal spacing everywhere.