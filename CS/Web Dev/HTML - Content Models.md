
HTML - content model = the behavior the browser applies to that element. All elements fall into two categories under the traditional content model - block level vs inline elements

Block-Level Elements:
- Render to begin on a new line
- Can contain inline or block level elements


Inline Elements
- Render on the same line by default
- May only contain other inline elements

HTML5 has replaced these with more complex categories but the distinction is still practical because it aligns well with CSS rules.

In HTML5, flow content roughly translates into block level while phrasing content roughly translates into inline elements.

For example, the div element is flow content which means because it is roughly the equivalent of a block-level element, text inside divs appear on new lines. This also means because the span element would roughly translate to an in line element, it can't contain a div element.

Useful chart: [3.2.5 Content models — HTML5 (w3.org)](https://www.w3.org/TR/2011/WD-html5-20110525/content-models.html)

To clarify, block level elements both start with a new line and any subsequent content will start on a new line after the element is closed.