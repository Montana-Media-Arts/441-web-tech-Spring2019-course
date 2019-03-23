---
title: HTML5 Collisions
module: 11
---

# Week 11 HTML5 Collisions

With any game, you need to be able to handle collisions. We are going to use a really simple box collider.  It basically checks the corners of the boxes to see if they are overlapping.  If they are, then it returns true, else it returns false.  Keep in mind, collision can be more precise but it takes more processing because of all the points that must be checked.  Also, collision must be checked whenever something moves.

Here is our collision code:

```javascript
function hasCollided(object1, object2) {
    return !(
        ((object1.y + object1.height) < (object2.y)) ||
        (object1.y > (object2.y + object2.height)) ||
        ((object1.x + object1.width) < object2.x) ||
        (object1.x > (object2.x + object2.width))
    );
}
```

Now, wait a minute.. you might have thought that objects were going away.. but what if I told you that you could create an object out of each of your squares (assuming you have at least two).  Then, you can send your objects into this function and it will check to see if you have collided or not.

So, first things first, we need a class.  Maybe call it Square and have 5 properties for x, y, height, width, and color.  Then, create your constructor and getters and setters.

Then, create two squares.  Make sure they show up on the screen. Then, make sure the first square can still move around.  It should respond to key events still.

Then, see if you can check for collision.  What happens if they collide?