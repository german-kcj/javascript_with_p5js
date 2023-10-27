---
description: 'let person = {name: ''Pepito'', age: 18, cool: true};'
cover: .gitbook/assets/js_with_p5js.png
coverY: 0
---

# Objects

<figure><img src=".gitbook/assets/Screen Shot 2023-08-03 at 11.18.13 AM.png" alt=""><figcaption></figcaption></figure>

## Objects

Objects are a fundamental concept used to represent real-world entities, ideas, or elements of your program. Objects allow you to group together related data (properties) and functions (methods) that operate on that data.&#x20;

They help to organize code and create reusable, modular components. Objects are particularly useful when you want to model different types of things with shared characteristics and behaviours.

* Objects can be explained as **blueprints** or **moulds** to create something. &#x20;
* **Properties** are the characteristics or attributes of the object.  For a car object, we can have the properties, colour, make, number of doors, is it electric, model.
* **Methods** are the actions the object can perform.  For our car example, we can have methods to start, accelerate, brake, honk and turn.

## Code

Explore the code below and identify the previously learned concepts.  What is different from the previous examples?  Notice the new elements:

#### From variables to Object

In the following code, we first create an object using variables (Commented Code) and then we reproduce the same code, but using an object

{% code overflow="wrap" lineNumbers="true" %}
```javascript
// CODE WITHOUT OBJECTS
/*
let bobX = 200;
let bobY = 200;
let bobR = 50;

function setup() {
  createCanvas(400, 400);
  background(42);
}

function draw() {
  // We create a circle with our variables and make it green
  fill(0, 255, 200);
  circle(bobX, bobY, bobR);
}
*/

// CODE USING AN OBJECT
// bob object with three properties: x, y, r;
// Objects have keys and values.  
// key x, value 100.  key y, value 100, key r, value 50
let bob = {
    x: 100,
    y: 100,
    r: 50,
  };

function setup() {
  createCanvas(400, 400);
  background(42);
}

function draw() {  
  // We create a circle using our bob object
  // We access the values in the object by using dot notation
  // We type the name of the object, a dot (.) and then the property we want to access
  fill(255,200,0);
  circle(bob.x, bob.y, bob.r)
}
```
{% endcode %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Object methods</summary>

In this example, we use **push** to **add** an element to the end of the emojis array and **pop** to **remove** one element from the end of the array.

{% code overflow="wrap" %}
```javascript
// Declare the variable bob
let bob;

function setup() {
  createCanvas(400, 400);
  background(42);
  
  // Add Properties (x, y and r)
  // Add Methods (show and move)
  bob = {
    x: random(width),
    y: random(height),
    r: 10,
    show: function () {
      fill(255, 255, 0);
      // We use the keyword 'this' to represent the object itself
      // In this case the keyword 'this' refers to bob
      circle(this.x, this.y, this.r);
    },
    move: function () {
      this.x += random(-5, 5);
      this.y += random(-5, 5);
    },
  };
}

function draw() {
    // Call the methods show and move on the object bob
    bob.show();
    bob.move();
}

```
{% endcode %}

</details>

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Classes</summary>

In this example, introduce the concept of Classes.  This is a way to create objects within modern JavaScript.

{% code overflow="wrap" %}
```javascript
let arr = [];

function setup() {
  createCanvas(400, 400);
  background(42);
}

// In modern JavaScript we can declare a class Bob
// The class Bob can create many copies of itself and
// as we see in this example it can take information from the user to 
// add different properties to each object
class Bob {
  // The constructor function within the class can take information
  // In this case it receives the value r, representing the desired radius
  // It has other two properties x and y
  constructor(r){
    this.x = mouseX;
    this.y = mouseY;
    this.r = r;
  }
  show(){
    circle(this.x, this.y, this.r);
  }
  move(){
    this.x += random(-1,1);
    this.y += random(-1,1);
  }
}

function draw() { 
  // A different way of using loops in modern JavaScript
  for(let bob of arr){
    bob.show();
    bob.move();
  }
}

function mousePressed() {
  // Each time the user presses the mouse on the canvas
  // a new object Bob is created and it receives a random value between 5 and 30 as its r (radius)
  let bob = new Bob(random(5,30));
  arr.push(bob);
}

```
{% endcode %}

</details>

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Add more objects.
2. Add more properties to the objects you created.
3. Add one more method that checks if the bob is within the canvas and returns true or false. Use that method to only move **bob** if it is within the canvas.
4. Add a new method of your liking.

### Links Projects on p5js&#x20;

* Objects [**LINK**](https://editor.p5js.org/Garcila/sketches/0ygpx\_rbP)
* Objects and methods [**LINK**](https://editor.p5js.org/Garcila/sketches/0JqxE45fE)
* Objects and classes [**LINK**](https://editor.p5js.org/Garcila/sketches/vSX44U3Sr)

### Deep Dive

{% hint style="info" %}
* From p5.js [**LINK**](https://p5js.org/reference/#/p5/object)
* From MDN [**LINK**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)
{% endhint %}
