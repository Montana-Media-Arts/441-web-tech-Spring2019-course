---
title: AJAX with jQuery
module: 9
jotted: false
---

# AJAX with jQuery

Now, the previous examples were a little more complicated wouldn't you agree?  How does JQuery help us with that?

Let's look at an example:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(document).ready(function () {
            $("button").click(function () {
                $("#bikeInformation").load("bikeInfo.txt");
            });
        });
    </script>
</head>

<body>
    <div id="bikeInformation">Nothing yet</div>
    <button>Get Bike Information</button>
</body>

</html>
```

The basic syntax of the JQuery AJAX call looks like this

`$(selector).load(URL,data,callback);`

This means we can find our elements, load some data from a URL, the data parameter, which is optional is sent with the URL, and then callback is a function to be called when the load is complete.

So, we could do something like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(document).ready(function () {
            $("button").click(function () {
                $("#bikeInformation").load("bikeInfo.txt", fadeText);
            });
        });

        function fadeText()
        {
            $("#bikeInformation").fadeOut("slow").fadeIn("slow");
        }
    </script>
</head>

<body>
    <div id="bikeInformation"></div>
    <button>Get Bike Information</button>
</body>

</html>
```
Here we are calling a function to be executed once the data has been retrieved and displayed.  Cool eh?

There are even more jQuery functions that you can used, but I will refer you to W3Schools to check them out.
[W3Schools JQuery AJAX](https://www.w3schools.com/jquery/jquery_ref_ajax.asp)