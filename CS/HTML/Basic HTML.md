HTML uses tags to display text and images contained in <> symbols - usually you wrap text with tags, starting with a beginning tag and ending with a closing tag. Closing tags usually contain a "/".

For example - <p>&lt;h1&gt; header &lt;/h1&gt;</p>
To display the literal text '< h >', you need to use HTML character entities, or else HTML interprets it as a header. When typing the text above without using character entities, the following is displayed:
<h1> header </h1>
HTML tags are not case sensitive but URLs generally are. When writing text it's a good convention to leave many blank lines between paragraphs.

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
**< p >**
