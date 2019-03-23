---
title: HTML5 Key Events
module: 11
---

# Week 11 Key Events

In the last section, we looked moving items across the screen. If you can do that, then you can move something with a key event too. Let's use our code frome before to draw a blue square:

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
            var x = 50;
            var y = 50;
            ctx.fillStyle = "#0000FF";
            drawSquare();
            
            function drawSquare()
            {
                ctx.clearRect(0,0,800,600);
                ctx.fillRect(x, y, 20, 20);
            }

        </script>
    </body>
</html>
```

Notice this time, we aren't moving the square automatically.  We are going to move it with keys!  Should we use WASD or arrows?  Or both?  Let's start with WASD.

So, you may recall that all keys (input) have to get translated for the computer to be able to know what key was pressed.  For example, we know that M was pressed or Q.  But each of those keys are mapped to a certain number and their numbers are stored as 0's and 1's so the computer knows what do to with them.

In JavaScript and jQuery, we have to either use their key's number or try and compare the actual letter.

```javascript
$(document).ready(function(){
    $(this).keypress(function(event){
        getKey(event);
    });
});

function getKey(event)
{
    var char = event.which || event.keyCode;
    var actualLetter = String.fromCharCode(char);
}
```

Remember `this`?  It's back!  This allows us to check for key events on anything that might be on the page.  Then, we can get the letter that was pressed and do something.

So, let me ask you this. If I wanted to go up, which letter would I press?  `w` right?  Which value would I need to change? **x** or **y**?  If you answered **y**, you are correct!  What do I need to do to **y** to make the shape move up?  Do I need to **add** to it or **subtract** from it?  Keep in mind that 0,0 is in the upper left hand corner.  If you answered **subtract** from **y**, you were correct!

So, the function might be like this:

```javascript
function getKey(event)
{
    var char = event.which || event.keyCode;
    var actualLetter = String.fromCharCode(char);
    if(actualLetter == "w")
    {
        moveUp();
    }
    drawSquare();
}

function moveUp()
{
    y-=10;
}
```
Did you notice I put the drawSquare function in after the if statement?  Why did I need to do that?

Okay so now you should be able to put the other letters in there and move your square character all around!  Exciting huh?

So, what about collisions?  Go to the next section and we will see about that!
