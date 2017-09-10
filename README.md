# Getting Started With Elm 
![elm lang](./images/logo.png)

## Introduction
Elm is an easy to use and robust functional language, created with the intentions of to ease the web development process. 



## Operators, Syntax and data types
### Basic operators
Elm uses almost all the standard symbols operators that Javascript and other languages uses
| Operator      | Used for            | Example     
| ------------- | --------------------|-------------------
| -             | Subtraction         |
| +             | Addition            |
| ++            | Concatenation       |
| /             | Decimal division    |
| //            | Integer division    |
|               | (discard decimals)  | 
| %             | Module              |
| rem           | Division remainder  |
| ^             | Exponentiation      |
| =             | Assign value        |
| ==            | Comparison          |


if statements

### Functions
Because Elm is a FP it relies mostly on functions, and that is why functions manipulation is 
  * Functions can be named (regular functions)
  * Functions can be use without giving any name( anonymous functions )
  * They can be passed as arguments.
  * They can return another function as result.
  * They can be stored in list and variables
  * Can be easily assing 


Loops

Arrays


List


Records

## What makes Elm different ?

One thing that is worth to highlight about Elm is its amazing performance. Elm, as most front end frameworks, has its own virtual DOM implementation, but compare to others is one of the fastest, this is due to the fact that all values are immutable , which has been proved to make JavaScript code faster. 


Another amazing feature about Elm is that it has no runtime exceptions, which means that the most commons errors don't make it to the user. That is because Elm checks all problems during compilation , and if its find any error, it would give you hints about the possible reason why your getting the error and the possible solutions for the same.
NOT MORE "undefined is not a function"


## Architecture
Elm architecture is based on the Model, View and Controller(MVC) design pattern, the difference is that instead of a controller it uses Update, similar to React.
The Model is the data the application will operate on and its behavior, this is call State"in other languages, Update defines what changes to make to the state given an action or an input, and in return it creates a new version of the state(remember that all values are immutable) with the resulting changes, the View defines what to render depending on the current state.


## Building Our First Elm App: (Hello, Elm!)
### Creating an elm app locally

First we want to install elm on computer. In our terminal:

`npm install -g elm`

To test to see if elm is installed, we write:

`elm -v`

Make a new directory for elm project and create a Main.elm file

`mkdir elm-project`

`touch Main.elm`

Now let’s cd into the folder and run:

`elm package install elm-lang/html`

You should recieve a prompt, saying:
```bash
Some new packages are needed. Here is the upgrade plan.

  Install:
    elm-lang/core 5.1.1
    elm-lang/html 2.0.0
    elm-lang/virtual-dom 2.0.4

Do you approve of this plan? [Y/n]
```
Hit `Y` to install the dependencies.
Now elm can compile to html and run in the browser

Writing our elm code from `Main.elm` looks like this:

```elm
module Main exposing (..)

import Html exposing (text)


main = 
    text “Hello, Elm!” 
```

As simple as that! Now let’s compile our code using this command:

`elm make Main.elm --output app.js`

`elm make` is compiling our code into a javascript file called `app.js` and now we can link to an HTML document.

At the root of our project directory we’ll create an `index.html` to store the script that the compiler generated for us from our Elm file.

```html
<!DOCTYPE html>
<html lang=“en”>
<head>
  <meta charset=“UTF-8”>
  <meta name=“viewport” content=“width=device-width, initial-scale=1.0”>
  <meta http-equiv=“X-UA-Compatible” content=“ie=edge”>
  <title>Hello Elm App</title>
</head>
<body>
  <div id=“app”></div>

  <script src=“app.js”></script>
  <script>
    var appContainer = document.querySelector(‘#app’)
    Elm.Main.embed(appContainer)
  </script>
</body>
</html>
```

We target our div that we created with an id of app in our script tags. We’re telling elm that we will embed our `Main.elm` file in that div that we assigned to a variable called `appContainer`.

That’s it. We created our first Elm app. Fire up your browser and open your html file and you should see “Hello, Elm!”.


## Module declaration
` module Main exposing (..) `
Every module in Elm starts with a module declaration and should be named the same as the file name.
e.g. `Main.elm` contains `module Main`
`exposing (..) ` exposes the functions and types to other modules importing. `(..)` means let’s expose everything

## Imports
`Import Html exposing (text)`
In the example above using `import Html `, we’re importing the Html module we want to use explicitly. We’re using the `text` type from the Html module so we import it to our application space using `exposing (text)`

## Main
```elm
main =
     text “Hello, Elm!”
```
Elm applications are rendered through the `main` function.  `main` returns an element to be placed on the page. 



