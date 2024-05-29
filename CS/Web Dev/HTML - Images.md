
In vscode, by typing "img" followed by pressing tab, the IDE will automatically fill in the rest.
In HTML5, the img tag is self closing and thus doesn't require a closing bracket.
Some important features to note are:

src - stands for source. What comes after src is the url for the image.

alt - used with the img tag to provide alternative text. Checked by screen readers and will also load in place of the image if the image fails to load.
here is an example of what alt text looks like if the img fails to load -
![[Example Alt Text.png]]

title - text complimentary to the image. Shows up when hovering over the image.

width/height - does exactly what the name says. Useful to provide even though they can be changed by css to prevent "cumulative layout shift", or to make sure the browser knows to make room for the image.

** you can view the width and height of an image in vscode in the bottom right of the screen. ![[Example Image.png]]

loading - either "lazy" or "eager". Any image below the "fold" should be set to lazy. Images are set to eager by default, which means the webpage will automatically load all the images. This is inefficient, and you want the webpage to only load images once you scroll to them - any image below the fold is just an image you are unable to see before you start scrolling.

----
If you want to add a caption or text related to the image, wrap using the figure tag and then create a figcaption tag - this is better than the paragraph tag since it lets screen readers know the text is related to the image.
A figcaption must be either the first element wrapped by the figure tag or the last.