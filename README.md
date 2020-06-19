# SASS Crash Course By <Traversy Media>

## Course Link - https://www.youtube.com/watch?v=nu5mdN2JIwM

## - What is SASS?
 - Syntactically Awesome StyleSheets
 - CSS preprocessor/extension

## - SASS vs SCSS
 - **SASS** is like stylus, pug template engine
 - **SCSS** is like nested css

## - Variables in css
 - Prefixed with a **_$_** 
 > Easier to read and write than CSS custom properties

## - Nesting

 ```javascript
 nav {
     ul {
        margin: 0; 
        padding: 0;
        list-style: none;
     } 
     li {
         display: inline-block;
     }
     a {
         display: block;
         padding: 6px 12px;
         text-decoration: none;
     }
 } 
 ```
 
## - Modules
 - CSS sends more request to server, but SASS is not sending much request. It handles it.
 - **_** sass file will be ignored during sass compilation
 ```javascript
 // _base.scss 
 $font-stack: Helvatica, sans-serif;  
 $primary-color: #333;  

 body {
     font: 100% $font-stack;
     color: $primary-color;
 }
 
 // Use it other sass file
 @use 'base' 
    .box{
        background-color: base.$primary-color;
        color: #fff; 
    } 
 ```

## - Mixins & Functions
 ```javascript
 @mixin transform($property){ 
    -webkit-transform: $property; 
    -ms-transform: $property; 
    transform: $property; 
 }
 .box { @include transform(rotate(30deg)); } 
 ```

## - Inheritance
 ```javascript 
 %message-shared { 
    border: 1px solid #ccc; 
    padding: 10px; 
    color: #333;
 } 
 .message { @extend %message-shared; } 
 .success { 
    @extend %message-shared;
    border-color: green; 
 } 
 .error { 
    @extend %message-shared;
    border-color: red; 
 } 
 ```

## - Operators
 ```javascript
 .container {
     width: 100%;
 }
 article[role="main"] { 
    float: left;
    width: 600px / 960px * 100%; 
 }
 aside[role="complementary"] { 
    float: right;
    width: 300px / 960px * 100%; 
 }
 ```

## - Conditionals
 ```javascript
 @mixin triangle($size, $color, $direction){
    height: 0;
    width: 0;

    border-color: transparent;
    border-style: solid;
    border-width: $size / 2;

    @if $direction == up {
        border-bottom-color: $color;
    } @else if $direction == right {
        border-left-color: $color;
    } @else if $direction == down {
        border-top-color: $color;
    } @else if $direction == left {
        border-right-color: $color;
    } @else {
        @error "Unknown direction #{$direction}.";
    }
 }

 .next {
     @include triangle(5px, black, right);
 }
 ```

> Can use it for toggle light / dark mode for web
