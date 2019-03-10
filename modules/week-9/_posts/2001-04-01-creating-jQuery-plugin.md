---
title: Creating jQuery Plugins
module: 9
jotted: false
---

# Creating jQuery Plugins

How about if we want to make our own though?  It can be quite simple.  Let's look at a small example:

```script
$.fn.bluey = function() {
    this.css( "background-color", "blue" );
};
```

What is happening here is that a function is being defined with the `$.fn` and then it is named `bluey`.  Not sure if that is a word or not.. but hey why not?!

Then, the function is created with the `function()` and the css is being applied to whatever element will use this function called bluey.

So, what does the whole page look like?

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
    <script>
        $.fn.bluey = function () {
            this.css("background-color", "blue");
        };

        $(function () {
            $("button").click(function () {
                $("#changeDiv").bluey();
            });

        });
    </script>
</head>
<body>
    <div id="changeDiv">Test information</div>
    <button id="btnSubmit">Click</button>
</body>
</html>

```

If you were to run this page, the background color of our div tag would turn blue and low and behold we have a new look based on our function.  We can have it apply to any tags we want.  And we can add more changes to the same jQuery plugin function.  It might look like this:

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $.fn.bluey = function () {
            this.css("background-color", "blue");
            this.css("color", "white");
            this.css("font-size", 24);
        };

        $(function () {
            $("button").click(function () {
                $("#changeDiv").bluey();
            });

        });
    </script>
</head>
<body>
    <div id="changeDiv">Test information</div>
    <button id="btnSubmit">Click</button>
</body>
</html>
```

Now, in order for this to work in a chaining situation and have it so that it survives in the real world, we have to make a couple of changes to the plugin.  First, we have to return `this`. This will return the object so that it more functions can be added to our plugin.  Then, it needs to be put into a immediately invoked function expression and then pass the function jQuery so that it knows that it is a jQuery plugin now and won't conflict with anything else.

It would look like this:

```script
    (function($){
        $.fn.bluey = function () {
            this.css("background-color", "blue");
            this.css("color", "white");
            this.css("font-size", 24);
            return this;
       };
    }(jQuery));
```

However, what this means is that we can do something like this now:

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
       
        (function($){
        $.fn.bluey = function () {
            this.css("background-color", "blue");
            this.css("color", "white");
            this.css("font-size", 24);
            return this;
        };
        }(jQuery));
        $(function () {
            $("button").click(function () {
                $("#changeDiv").bluey().fadeOut("slow").fadeIn("slow");
            });

        });
    </script>
</head>
<body>
    <div id="changeDiv">Test information</div>
    <button id="btnSubmit">Click</button>
</body>
</html>
```

At this point, you can create a simple jQuery plugin.  C'mon that's pretty cool!
