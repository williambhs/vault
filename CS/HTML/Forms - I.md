Form controls - used to collect information
When a user fills out and submits a form, info is sent to the server

Form controls go inside the < form > element. All form elements require an action attribute, with the URL of the action attribute being the page on the server receiving info from the form.

Forms can be sent with either the get or post methods. To specify which, in the opening tag use attribute method="get" or method="post".

1] get: with the get method, values are added to the end of the URL. You should use the get method for short forms like search boxes and when you are just retrieving data, not sending information 

2] post: should be used if your form allows for file upload, is log, contains sensitive data like a password, or is adding information to/deleting information from a database

if no method is specified, the form data will default to using the get method.

id attribute - used to identify the form from other elements ** update later

**input element** - used to create different form controls depending on what's nested within the input tags. 
relevant tags - 

1] type: the value of the type attribute determines what kind of input will be created
some examples of values that can be passed into the type attribute include:

type = "text" - creates a single line text input


