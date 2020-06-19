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

 ``` nav {```
 ```    ul {```
 ```       margin: 0; ```
 ```       padding: 0;```
 ```       list-style: none;```
 ```    } ```
 ``` } ```
 
## - Modules
 - CSS sends more request to server, but SASS is not sending much request. It handles it.
 - **_** sass file will be ignored during sass compilation
 ``` // _base.scss ```
 ``` $font-stack: Helvatica, sans-serif;  ```
 ``` $primary-color: #333;  ```

 - Use it other sass file

 ``` @use 'base' ```
 ``` .box{background-color: base.$primary-color; } ```

## - Mixins & Functions
 ``` @mixin transform($property){ transform: $property; } ```
 ``` .box { @include transform(rotate(30deg)); } ```

## - Inheritance
 ``` %message-shared { border: 1px solid #ccc; padding: 10px; color: #333} ```
 ``` .message { @extend %message-shared; } ```

## - Operators
 ``` article[role="main"] { width: 600px / 960px * 100%; }```

## - Conditionals
 - Can use if/else

 
