# HTML Notes

`<em>` and `<i>` both do the same thing but the `<em>` should be used instead 

`<strong>` and `<b>` both do the same thing but the `<strong>` should be used instead 

`<link rel="stylesheet" type="text/css" href="style.css">` - External CSS file 

`<script src="animations.js"></script>` - External JS file 

### Basic HTML5 website template 

``` html
<!DOCTYPE html> 
<html> 
    <head> 
        <meta charset="utf-8"> 
        <title>Title Name</title> 
    </head> 
    <body> 
        <h1>Hello!</h1> 
    </body> 
</html> 
```

When making a form that has radio buttons and you only want one option to be selected at a time, they must all have the same name attribute. 

``` html
<form> 
    <label for="dogs">Dogs:</label> 
    <input type="radio" name="petChoice" id="dogs"> 
    <label for="cats">Cats:</label> 
    <input type="radio" name="petChoice" id="cats"> 
    <button>Go!</button> 
</form> 
```

In order for HTML to know which radio button option is selected, all of the options need to have value attributes selected 

``` html
<form> 
    <label for="dogs">Dogs:</label> 
    <input type="radio" name="petChoice" id="dogs" value="dogs"> 
    <label for="cats">Cats:</label> 
    <input type="radio" name="petChoice" id="cats" value="cats"> 
    <button>Go!</button> 
</form> 
```

When making a dropdown box we use the select tag. In the select tag the name attribute needs to be set `<select name="mood">` 

If you do not want to use the text that is in-between the option tags, you need to use the value attribute 

``` html
<select name="mood"> 
    <option value="happy">:)</option> 
    <option value="neutral">:|</option> 
    <option value="sad">:(</option> 
</select> 
```

To create a text area, we use the `<textarea>` tag. You have to type the name attribute, the number of rows and the number of columns `<textarea name="text" cols="30" rows="10"></textarea>`

Use a container div do that there will be a margin on each side of the content 