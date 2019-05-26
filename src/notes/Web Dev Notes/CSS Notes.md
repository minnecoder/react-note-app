# CSS Notes

Using the star `*` selects every item on a webpage

A descendant selector is selecting an element within an element. The below example selects all of the anchor tags that are within an li element

``` css
li a {
    color: red;
}
```

An adjacent selector is selecting the second element that is on the same level as the first element. The example would select all of the `ul` elements that follow an `h4` element.

``` css
h4 + ul {
    color: blue;
}
```

An attribute selector is selecting all elements that are of the element type that is selected and have an attribute that match. The example would select all anchor tags that have links to Google's website 

``` css
a[href="http://www.google.com"]{ 
    background: beige; 
}
```

The nth of type is a selector that will select the number of each group that is selected. For example the code that is below will select the third li of each group.  

- This can be done with any number or even using the words odd or even to select every other item. 

``` css
    li:nth-of-type(3){
        background: purple;
    }
```

If there is an element that is selected that is on a higher level, it will make those changes to the children of that element. For example, setting the color of the font for the body, will make all of the font that color.

There are levels of specificity when it comes to selectors. The levels of specificity are shown below: 

1. Universal selectors (i.e. *) 

2. Type selectors (i.e. h1) and pseudo-elements(i.e. :before) 

3. Class selectors(.special), attribute selectors (`a[href="http://www.google.com"]`), and pseudo-classes(`:hover`)  

4. ID selectors (#highlight) 

    **<u>Useful Links</u>**


    The 30 CSS Selectors you must memorize
    https://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048 


When using a container, which should be always, use the following CSS: 

``` css
.container{ 
    width: 80%; 
    margin: auto; 
    overflow: hidden; 
} 
```

`Text-decoration: none;` will remove all of the underlines from links 

The CSS selectors that are needed to make a horizontal navigation bar is: 

```css
ul{ 
    margin: 0; 
    padding: 0; 
} 

header a{ 
    text-decoration: none; 
    text-transform: capitalize; 
    font-size: 16px; 
} 

header li{ 
    float: left; 
    display: inline; 
    padding: 0 20px 0 20px; 
} 
```


**<u>CSS Positioning</u>** 

The most used type of positioning is static where the document flow is followed.  

The other type of position types are: absolute, relative, and fixed 

When using positioning other than static, the things that are changed are Document Flow and Positioning Context 

Document Flow uses the contexts of top, right, bottom, and left 

Position Context uses the portion of the screen where the selected element should be placed (i.e. `viewport`, `<html>`, or `<body>`).  

Fixed is based on the position of the viewport. With `top:0`, the item will stay on the top of the screen as you scroll 

Absolute is based on the position of its containing element. For example with a `nav` that is held within the `body` tag, the `nav` will be in the upper left corner with `top: 0` and `left: 0` 