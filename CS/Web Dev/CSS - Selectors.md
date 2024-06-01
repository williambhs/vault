
Selector - pattern or rule used to target all instances of a specific HTML type
Ex. 'p' targets all '< p >' elements.
Read from right to left - for example '.colored p' means every element p inside class colored will be affected, because p is the rightmost element referenced and colored is the leftmost element referenced.

<h1> Types of selectors: </h1>

**Element Selector** - targets all instances of a specific HTML element type (reference the example above for paragraph elements)
p {
	color: blue;
}

**Class Selector** - targets all elements with a specific class attribute - done with a period
.exampleClass {
	color: blue;
}

**ID Selector** - targets all elements with a specific ID attribute. Remember - IDs are unique and no two elements can have the same id.
'#'example id
<!-- ignore the quotation marks, they're there to duck the obsidian formatting -->
{
	color: blue;
}

**Descendant Selector** - targets all elements that are descendants of a parent element. 
An element that is a descendant element is any element nested within another HTML element at any depth.
div p {
	color: blue;
}

The following code will apply the color blue to each p element is a descendant of a div element.

**Child Selector:**
Targets elements that are direct children of a parent element. The difference between a child selector and a descendant selector is that a child selector only affects elements that are **direct** children, meaning they must be the first "level" in the nest.

div > p {
	color: blue;
}

The following code will apply the color blue to p elements that are DIRECT descendants of div elements.


**Combining Selectors:**

**Element w/ Class Selector:**

p.exampleClass {
	color: blue;
}

The above changes every p with class exampleClass to blue. Note that there is no space between the element and class definition. If you were to add a space, p .big would target all elements of class big that are descendants of p.

Keep in mind - when you do something like:
div.exampleClass p
{
	color: blue;
}

This will only apply to p elements nested in div elements with example class. That means if span has the class attribute exampleclass and is nested within a div element with a p element inside, such as:

< div >
	< span class = "exampleClass">
			< p > Hello < / p >
	< / span >
< / div>

The hello text inside the p element would not show up as blue.