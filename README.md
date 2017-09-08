# Getting Started With Elm

## Introduction
Lorem ipsum dolor sit amet consectetur adipisicing elit. At quam, delectus quod consequatur asperiores doloremque eaque deleniti assumenda eum, cupiditate fugit laboriosam in, quidem nihil ad explicabo consectetur consequuntur earum!

## Building Our First Elm App (Hello, Elm!)
### Creating an elm app locally

*First we want to install elm on computer*
1. NPM install elm (or run the install on elm-lang.org)
> npm install -g elm (Unix based system)

*Test to see if elm is installed*
> elm -v

2. Make a new directory for elm project and create a Main.elm file
> mkdir elm-project
> touch Main.elm

3. Install html dependency

*Elm uses html dependency in order to be able to compile and ran on the browser.
http://package.elm-lang.org has a list of packages you can install with Elm but the package we want can be install using the following command in the terminal*

> elm package install elm-lang/html

*_Should ask you the following_*

```
Some new packages are needed. Here is the upgrade plan.

  Install:
    elm-lang/core 5.1.1
    elm-lang/html 2.0.0
    elm-lang/virtual-dom 2.0.4

Do you approve of this plan? [Y/n]
```

*Hit Y to install the dependencies.
Now elm can compile to html and run in the browser*

4. Writing our elm code from 'Hello, Elm!' looks like this:

```elm
module Main exposing (..)

import Html exposing (Html, span, text)
import Html.Attributes exposing (class)


main : Html a

main = 
    span [ class "welcome-message" ] [ text "Hello, Elm!" ]

```

5. After writing your elm code, compile your program using the followng command:
> elm make Main.elm — output app.js

*Which compiles our elm code into a javascript file we can link to an HTML document we create.*

6. At the root of our project directory we'll create an index.html to store the script that the compiler generated for us from our Elm file.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Hello Elm App</title>
</head>
<body>
  <div id="app"></div>

  <script src="app.js"></script>
  <script>
    var appContainer = document.querySelector('#app')
    Elm.Main.embed(appContainer)
  </script>
</body>
</html>
```

*We target our div that we created with an id of app in our script tags. We're telling elm that we will embed our Main.elm file in that div that we assigned to a variable called appContainer.*

*That's it. We created our first Elm app. Fire up your browser and open your html file and you should see "Hello, Elm!".*