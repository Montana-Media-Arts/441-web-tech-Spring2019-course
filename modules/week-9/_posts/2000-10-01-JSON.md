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


```




