---
title: JSON Review
module: 9
jotted: true
---

# JSON Review

Before we look at how to access data using AJAX, we will review JSON. Recall JSON is JavaScript Object Notation.  This is a way to store data as an object.

Remember, JSON is a standardized method for storing and transporting unordered collections of data. This data is stored through _name:value_ pairs. Furthermore, the _values_ in JSON data can be;

- strings
- numbers
- booleans
- arrays
- or other nested JSON objects


<br />


JSON Objects, once in JavaScript (i.e. after being sent over from an API on a remote server), appear as JS objects. As such, they can be traversed and manipulated using standard JS object notation and techniques.

As an example, the following code creates a JS Object, which is also valid as JSON.

```js
let bike = {
    "manufacturer" : "Santa Cruz",
    "model" : "5010",
    "owner" : {
        "firstName" : "Bob",
        "lastName" : "Jones"
    },
    "sizes" : [
        "small",
        "medium",
        "large",
        "x-large"
    ]
}
```

Once this object is binded to the variable `bike`, we can navigate through it and access it unique values.

The following example creates the same object as above, but also demonstrates how to access values within the object.

```html
<html>
    <head>
        <script>
            let bike = {
                "manufacturer" : "Santa Cruz",
                "model" : "5010",
                "owner" : {
                    "firstName" : "Bob",
                    "lastName" : "Jones"
                },
                "sizes" : [
                    "small",
                    "medium",
                    "large",
                    "x-large"
                ]
            }

            function showBikeInfo()
            {
                document.getElementById("bikeInformation").innerHTML = "Manufacturer: " + bike.manufacturer 
                + "<br>Model:" + bike.model + "<br>First Name:" + bike.owner.firstName + "<br>Last Name:" 
                + bike.owner.lastName + "<br>Sizes Available:<br>" +
                bike.sizes[0] + "<br>" + bike.sizes[1] + "<br>" + bike.sizes[2] + "<br>" + bike.sizes[3];
            }
        </script>
    </head>

    <body>
        <div id="bikeInformation"></div>
        <button id="btnSubmit" onclick="showBikeInfo();">Show Information</button>
    </body>
</html>
```
This shows us how we can get to not only traditional JSON key/value pairs, but also JSON inside of JSON and an array inside of JSON.  That is good stuff!

But that's not all!  What about if we were do this in jQuery?  You could do it right?

Let's look at an example:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
         let bike = {
                "manufacturer" : "Santa Cruz",
                "model" : "5010",
                "owner" : {
                    "firstName" : "Bob",
                    "lastName" : "Jones"
                },
                "sizes" : [
                    "small",
                    "medium",
                    "large",
                    "x-large"
                ]
            }
        
        $(function () {
            $("button").click(function () {
                showBikeInfo();
            });

        });
       
        function showBikeInfo()
            {
                $("#bikeInformation").html("Manufacturer: " + bike.manufacturer 
                + "<br>Model:" + bike.model + "<br>First Name:" + bike.owner.firstName + "<br>Last Name:" 
                + bike.owner.lastName + "<br>Sizes Available:<br>" +
                bike.sizes[0] + "<br>" + bike.sizes[1] + "<br>" + bike.sizes[2] + "<br>" + bike.sizes[3]);
            }
        </script>
    </head>

    <body>
        <div id="bikeInformation"></div>
        <button id="btnSubmit" onclick="showBikeInfo();">Show Information</button>
    </body>
</html>

```

Keep in mind that I used the `.html` function so that I could display the break tags correctly.  Otherwise, everything else was pretty much the same.  You guys should be really pumped about this.  It's all coming together.  So, why do we review JSON?  Well, as we talked about before, it's a very common delivery method from many different sources so we can read information from databases and server-side pages because they will give information back to the client via JSON.  So, let's look at AJAX.


