
<h1> Overview </h1>

Form controls - used to collect information
When a user fills out and submits a form, info is sent to the server

Form controls go inside the < form > element. All form elements require an action attribute, with the URL of the action attribute being the page on the server receiving info from the form. If left empty, the form will submit to the current page.

Forms can be sent with either the get or post methods. To specify which, in the opening tag use attribute method="get" or method="post".

1] get: with the get method, values are added to the end of the URL. You should use the get method for short forms like search boxes and when you are just retrieving data, not sending information 

2] post: should be used if your form allows for file upload, is log, contains sensitive data like a password, or is adding information to/deleting information from a database

if no method is specified, the form data will default to using the get method.

id attribute - used to identify the form from other elements ** update later

**input element** - used to create different form controls depending on what's nested within the input tags. 


<h2> Relevant Tags </h2>

**type:**
type = "text" - creates a single line text input
type = "password" - creates a text box that acts like a single-line text input, except characters are hidden 
type = "radio" - allows users to pick one out of a number of options
used in conjunction with a name attribute, value attribute, and checked attribute - the value attribute indicates the value sent to the server and the checked attribute if set to checked (checked = "checked") will check an option by default once the page loads
type = "checkbox" - similar to radio, but allows users to select multiple options
type = "file" - allows users to upload files

**maxlength:**
maxlength = "some number" - limits the number of characters a user can enter into the text field

**name:**
name = "some random name" - indicates the name of the input - the server needs to know which form control each piece of data each piece of data was entered into to differentiate from for example what was entered as a username vs password

**textarea**
< textarea > enter text here < /textarea > - important to note that the textarea element is not an empty element and needs a closing tag. The text between the opening and closing tags will appear in the text box when the page loads. Note that if the user doesn't delete text between the tags the text will get sent to the server, which is why some sites use JS to clear the information when the user clicks into the text area.

**drop down list**
< select > 
< option > text < /option >
< /select >
note that the select and option elements are not empty tags and thus require closing tags as well. 
The select element is used to create a drop down list box, with the option element used to specify options.
The select tag needs a name attribute, just like other types, and the option tag needs a value element to indicate what value is being sent. Similarly to the checked attribute, there is a selected attribute for a drop down list to automatically have a box checked. (selected="selected")

To create a multiple select box, use the multiple option in the select tag (multiple="multiple")

