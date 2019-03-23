---
title: HTML5 Canvas
module: 11
---

# Week 11 HTML5 Canvas

The HTML5 Canvas is a revolutionary tag element that provides a number of benefits such as:

- HTML Canvas Can be Animated
-- Canvas objects can move. Everything is possible: from simple bouncing balls to complex animations.

- HTML Canvas Can be Interactive
-- Canvas can respond to JavaScript events.
-- Canvas can respond to any user action (key clicks, mouse clicks, button clicks, finger movement).

- HTML Canvas Can be Used in Games
-- Canvas' methods for animations, offer a lot of possibilities for HTML gaming applications.

Let's take a look at the most basic set up of the canvas.  If you want the canvas to appear, you just need the canvas tag.  It looks like this:

```html
<html>
    <head>
        <title>Canvas</title>
    </head>
    <style>
        #myCanvas{
            border:black;
            border-style: solid;
            border-width: 2px;
        }
    </style>
    <body>
        <canvas id="myCanvas" height="600" width="800"></canvas>
    </body>
</html>
```

Okay, so I get that you might not be all that impressed.  However, what if I wanted to put something onto the screen?  Here is where your JavaScript skills become handy.

If you alter the page to look like this now, your should have a blue square somewhere on the page.  Hwoever, you can change the first two numbers and the square should move around the canvas.

```html
<html>
    <head>
        <title>Canvas</title>
    </head>
    <style>
        #myCanvas{
            border:black;
            border-style: solid;
            border-width: 2px;
        }
    </style>
    <body>
        <canvas id="myCanvas" height="600" width="800"></canvas>

        <script>
            var canvas = document.getElementById("myCanvas");
            var ctx = canvas.getContext("2d");
            ctx.fillStyle = "#0000FF";
            ctx.fillRect(50, 50, 10, 10);
        </script>
    </body>
</html>
```

What was the ctx variable?  In order for us to interact with the canvas, we have to get the context of the canvas in 2d (3d requires a library and WebGL to help us).

So, what else can we do?

