HTML uses tags to display text and images contained in <> symbols - usually you wrap text with tags, starting with a beginning tag and ending with a closing tag. Closing tags usually contain a "/".

For example - <p>&lt;h1&gt; header &lt;/h1&gt;</p>
To display the literal text '< h >', you need to use HTML character entities, or else HTML interprets it as a header. When typing the text above without using character entities, the following is displayed:
<h1> header </h1>
HTML tags are not case sensitive but URLs generally are. When writing text it's a good convention to leave many blank lines between paragraphs.
See: [[Entities]]

<h1> Tags </h1>
**note - uses < h1 > so the text appears larger.**

<h2> Document Structure </h2>

<h3> DOCTYPE </h3>
Every webpage must start with a DOCTYPE declaration, even before the html tag. This tells browsers what version of HTML the webpage is in which helps them know how to process code. This looks like <!DOCTYPE html> in HTML5.

<h3> HTML Tag </h3>
**< html >**
Not required by all clients but common convention to include one at the start of a document or file. The < html > tag signals the point where text should start being interpreted as HTML. 

<h3> Head Tag </h3>
**< head >**
The first of two main sections of an HTML document used to provide info about the document, used mostly by search engines/browsers. Has the purpose of holding the title tag.
Some things commonly under the head tag include the title tag, metadata, etc.
<h3> Title Tag </h3>
**< title >**
Specifies the title of a web page which is displayed on the browsers title or tab (the text shown at the top of the tab). Also used by search engines to understand the content of the page. 
1 - SEO/Search Engine Optimization - the title appears as the clickable headline in search engine results pages
2 - Bookmarks - when users bookmark a page, the title is usually the default name of the bookmark
The title doesn't usually appear in the document itself but rather only at the top of the tab.

<h3> Body Tag </h3>
**< body >**
Defines the beginning and end of the document. Text, images, links, etc. should be in the body. Typically the body starts after the head and contains a majority of what is in the document.

<h2> Content/Container Tags </h3>
<h3> Headers </h3>
**< h1-6 >**
Up to six levels of headers h1 through h6 - h1 is the largest and they get progressively smaller. Headers are used for headings, not to make text bold - there is a specific tag to bold text.

<h3> Paragraphs </h3>
**< p >, < br >**
Used for "normal" text - < p > causes a line break and adds a trailing blank line while < br > causes a line break with no trailing blank line. As a convenience it's good convention to add 2-3 blank lines between paragraphs to facilitate editing. Unlike the paragraph tag, the br tag is empty and has no closing tag.

<h3> Preformatted Text </h3>
**< pre >**
Preformatted text allows you to keep text formatted. Simply wrap text with < pre > text < /pre > instead of < p > text < / p>. When using the paragraph tag, text you manually format loses any line breaks, indentation, etc, while using the preformatted text tag preserves any extra spaces.

<h3> Boldface, Italics, Underline, Strike-Through </h3>
**< b >, < i >, < u >, < strike >, < strong >, < em >**
< b > boldens text, < i > italicizes text, < u > underlines text, < strike > displays text with a strike. < strong > bolds text as well and < em > italicizes text, but they are distinct in that they have semantic importance as well - the strong tag indicates bolded text is not just bold but also significant, and the em tag indicates wrapped text should be emphasized, whereas the b and i tags are solely used for stylistic purposes.

<h3> Div </h3>
**< div >** 
Helps in organizing html documents - serves as a generic container with no semantic meaning. One of the primary uses is to apply CSS styles and layout properties by assigning different classes or IDs to < div > elements.

<h3> Span </h3>
**< span >** 
An inline container used to group elements for styling purposes. Does not provide any visual changes itself but is useful when utilized in conjunction with CSS and JavaScript to control the appearance and behavior of content. CSS styles can be applied to span elements using classes, IDs, or inline styles, and span elements can also be easily targeted and manipulated with JavaScript.

<h3> Lists </h3>
**< ul >, < ol >, < li >**
Lists are used to group related items in a structured manner. Ordered lists (< ol >) are used for lists where the order of items are important, unordered lists (< ul >) are used otherwise. 
The only difference between an ordered list and unordered list is that ordered lists are numbered while unordered lists are bulleted. 
The syntax for items in the list is < li > ListItem < /li >. Keep in mind items with the < li > tag must be nested inside some form of list.

<h3> Comments </h3>
<!-- text goes here -->
Anything between the tags is not displayed on the screen. Useful for notes, both to yourself and others who might view the source code of the page.

<h3> Semantic Tags </h3>
**< header >, < nav >, < main >, < aside >, < footer >**
HTML5 introduced new tags called semantic tags - functions similarly to div but generally seen as better practice to use semantic tags.
Similar to div as they provide a consistent structure that can be targeted with CSS/JavaScript - for example you can style all < header > elements consistently across a site.
The introduction of semantic tags has generally made the div tag obsolete. The usage of each tag is as follows:

*header* - contains introductory content 
*nav* - contains navigation content, such as a website navigation menu
*main* - contains the main content of a document - only one main element should be used in each document
*aside* - contains content tangentially related to the main content of the page