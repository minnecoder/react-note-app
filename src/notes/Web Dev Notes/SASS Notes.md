# SASS Notes

The NPM package `node-sass` can be used so that the sass files that are in the sass folder of the project will be compiled into CSS files. 

To get this to work the following code needs to be entered into the `package.json` file under the `scripts` section: 

`"scss": "node-sass --watch scss -o css"`

SASS allows for the nesting of CSS selectors

```scss
h1 {
    color: red;
    h2 {
        color: blue;
    }
}
```

SASS allows for the the use of variables. Variables are set in the syntax of `$<variable name>:<variable value>; ` Variables are called using the following syntax `color: $<variable name>` 

With SASS math can be used to change variable values and in any other place where math needs to be done.

Mixins are useful for when dealing with things like box shadow that have 3 different vendors. In stead of having to type each one out for every box shadow, a mixin can be used. An example of a mixin is typed like:

```scss
@mixin box-shadow($x, $y, $blur, $c) {
    -webkit-box-shadow: $x, $y, $blur, $c;
    -moz-box-shadow: $x, $y, $blur, $c;
    -ms-box-shadow: $x, $y, $blur, $c;
    box-shadow: $x, $y, $blur, $c;
}
```

To use a mixin within a selector, the syntax that is used is: `@include box-shado(10px, 10px, 4px, gray);`

Partials are files that can have portions of SASS code in them, these have file names that have the first character in the file name of an underscore. To use a partial within another SASS file the `@import` command is used at the top of the file. An example of this is `@ import "mixins";`

Within mixins there is the ability to use if, else if and else within a mixin. To use the three conditional statements, there needs to be an `@` before each of the words. So they would all  look like this: `@if @else if @else`

Another thing that can be with SASS is the use of for loops. Like the conditional statements, the word for has an `@` before the word for. An example of  a for loop that will make the bootstrap type column widths would look like this:

```scss
@for $i from 1 through 12 {
    .col-#{$i} {
        width: 100%/12 * $i;
    }
}
```

