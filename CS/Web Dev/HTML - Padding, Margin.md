**Padding** is the space **inside** the content of an element and its border - it is inside the element and directly surrounds the content.
The main use of padding is to ensure the content inside the element doesn't touch the edges of the element.

**Margin** is the space **outside** the border of an element that separates it from surrounding elements. Margin does not increase the size of the element but does move adjacent elements away. The margin color is always transparent, and you can specify margins for all sides


Here is a diagram of margin and padding -
+---------------------------------------+
|           Margin (transparent)        |
|  +-------------------------------+    |
|  |         Border (visible)      |    |
|  |  +-------------------------+  |    |
|  |  |    Padding (colored)    |  |    |
|  |  | +---------------------+ |  |    |
|  |  | |     Content         | |  |    |
|  |  | +---------------------+ |  |    |
|  |  +-------------------------+  |    |
|  +-------------------------------+    |
+---------------------------------------+


When assigning padding - it's useful to use the acronym TRouBLe - 
Top
Right
Bottom 
Left
Instead of having to type out individual padding on each side - you can just type it out all in one line like the following:
padding: 30px 10px 10px 10px;
This is the equivalent of:
padding-top: 30px;
padding-right: 10px;
padding-bottom: 10px;
padding-left: 10px;

This applies to margin as well.
Some other useful shortcuts to note - 

One value - applies the same padding/margin to all four sides 
Ex. padding: 20 px;
Applies padding of 20 px to all sides

Two values - first value applies to top/bottom, second applies to left/rght
Ex. margin: 20 px 30px;
Applies margin of 20 to top and bottom, and 30 to left and right

Three values - first value applies to top, second to left and right, third to bottom
Ex. padding: 20 px 10 px 30 px;
Applies padding of 20 to the top, 10 to the left and right, and 30 to the bottom

