To use Materialize CSS, the first thing to do is to past the below code into the `index.html` file. 

```html
<!DOCTYPE html>
<html>
  <head>
    <!--Import Google Icon Font-->
    <link
      href="https://fonts.googleapis.com/icon?family=Material+Icons"
      rel="stylesheet"
    />
    <!--Import materialize.css-->
    <link
      type="text/css"
      rel="stylesheet"
      href="css/materialize.min.css"
      media="screen,projection"
    />

    <!--Let browser know website is optimized for mobile-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </head>

  <body>
    <!--JavaScript at end of body for optimized loading-->
    <script type="text/javascript" src="js/materialize.min.js"></script>
  </body>
</html>
```

To use the CDN version of Materialize, replace the style sheet link and the JavaScript link with the links below:

```html
<!-- Compiled and minified CSS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css">

    <!-- Compiled and minified JavaScript -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js"></script>
```

### Color

##### Background

To make a div a specific color give the element a class of the color that is desired. For instance to make a div with a blue background, it would look like `<div class="blue darken-2t">Div with color class</div>`. There also is the option to lighten or darken the color by adding the `darken` or `lighten` class and a level of darken or lighten. Lighten has 5 levels of lighten (1 through 5) and darken has 4 levels of darken (1 through 4). An example of this is `darken-1`. 

##### Text Color

The color of the text can be changed by adding the class name of `<color of text>-text` an example of this is `blue-text`

### Buttons

To be able to use Material Icons there needs to be a link like this ` <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">` in the head section of the web page. 

The color of the background and the color of the text of the button can be changed by adding a class name with the color that the background should be. The color of the background can be lightened and darkened by the desired level.  

The size of the button can be made smaller or bigger by using `btn-small` and `btn-large`

There are other types of buttons that can be used. The first is the Flat Button which doesn't have a visible border or a different background color. It just is the text part of a link on the background. A flat button is made with the class name of `btn-flat` l789v8 0666666666fv  cbThe other type of button is a disabled button that is gray in color and is unable to be clicked