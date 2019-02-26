---
title: Learning jQuery
module: 8
jotted: false
---

# Learning jQuery

Previously, we looked at the basics of accessing items through the DOM. What other functions are available to us?  We looked at toggle?  What other methods are there?

Methods:

1. fadeIn()
2. fadeOut()
3. fadeToggle()
4. fadeTo()
5. slideDown()
6. slideUp()
7. slideToggle()
8. animate()

Then, we will look at some Callback functions and Chaining.

Yes, more terminology, but all good stuff!

So, what do they look like?

Here is an example:


```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                $(".myGreatClass").fadeOut();
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```

Now, try some of these other methods.  In the video below, I will go through a number of them.


What about animate?  It is a little different than the other methods listed above.  Let's look at it closer.


```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                $(".myGreatClass").animate({left: '250px'});
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass" style="background-color:red;position:absolute; top: 100px; left: 25px">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```

Again, this just shows that we are updating the style of this particular tag, but in a cooler way. 
