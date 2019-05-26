# Bootstrap Notes

If you are using the files locally for Bootstrap, the 2 files that are required are `bootstrap.css` and `bootstrap.min.css`

- A form with the class of `form-inline` will make all of the form elements on one line
- The class  `form-control` on the inputs in BS make them "bootstrapified"
- A div with a class of  `form-group` adds spacing and padding to the form elements
- The `jumbotron` class adds spacing to the sides of the element 

To use the dropdown and "hamburger" navbar elements we need the BS JS file, which also requires jQuery.

The jQuery CDN is found at <https://code.jquery.com> click on the newest version and click on uncompressed. Copy the URL of the next page and paste it into the end of the body tag. The link for the BS JS file also needs to be placed at the end of the body tag, after the link for jQuery. 

To make a navbar that is able to collapse, there are 2 things that need to be included, the "hamburger" button that shows the menu items after the navbar has been collapsed and the navbar with the correct classes

The data-target attribute on the button element has to be same as the id attribute on the div that has the collapsible navbar. The id attribute will not have the # in the name.

 ``` html
<button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-nav-demo" aria-expanded="false">
	<span class="sr-only">Toggle navigation</span>
	<span class="icon-bar"></span>
	<span class="icon-bar"></span>
	<span class="icon-bar"></span>
</button>
 
<div class="collapse navbar-collapse" id="bs-nav-demo">
	<ul class="nav navbar-nav">
		<li>About</li>
		<li>Contact</li>
		<li>Sign Up</li>
		<li>Login</li>
	</ul>
</div>

 ```





