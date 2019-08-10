# javascript-what-the-heck-is-this


JavaScript’s `this` keyword is a source of confusion for a lot of javascript developers. It can be frustrating if, for some reason, this doesn’t point to the context that was intended.

Why this keyword in JavaScript is a confusing thing?

Because the `this` keyword is always different depending on the scope involved. 


Actually it's quite simple. `this` always refers to the object context in which the code is executing, that say, **`this` always point to the *last object* that called it**

Lets deep dive into what the heck is `this` in the JavaScript magic world with examples.


```
var name = "Global";
function logThis() {
    var name = "Local";

    console.log(this.name);          // Global

    console.log("inner:" + this);    // inner:[object Window]
}
logThis();
console.log("outer:" + this)         // outer:[object Window]
```
Why this.name is `Global`, not `Local`? As we mentioned above: **`this` always point to the *last object* that called it**, when we call `logThis`, there isn't any object in front, so it will fall back to global object which is `Window`, so `logThis()` equal to `window.logThis()`.