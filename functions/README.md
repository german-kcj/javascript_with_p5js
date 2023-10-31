---
description: function draw(){circle(200,200,200);}
cover: ../.gitbook/assets/js_with_p5js.png
coverY: 0
---

# Functions

<figure><img src="../.gitbook/assets/Screen Shot 2023-08-03 at 4.21.02 PM.png" alt=""><figcaption></figcaption></figure>

## Functions

Functions are blocks of code that perform a specific task or set of tasks. They let us organize code into manageable and reusable chunks, making code more modular and easier to understand.&#x20;

p5.js comes with a set of built-in functions that you can use to create visual and interactive experiences.

#### Built-in Functions

p5.js provides a variety of built-in functions that you can use to draw shapes, manipulate colours, create animations, handle user input, and more. **createCanvas**, **background**, **circle**, **rect**, **fill**,  and **stroke** are all built-in functions.

#### Defining or Declaring Your Own Functions

You can also define your own custom functions to encapsulate specific actions that you want to perform repeatedly.&#x20;

{% code overflow="wrap" lineNumbers="true" %}
```javascript
// We define the function "mySuperFunction" with one parameter.
// Parameters are variables or placeholders for information that we'll provide to the function
function mySuperFunction(parameter){
  // Do something
}
```
{% endcode %}

**Calling Functions**

Once a function is declared or defined, it needs to be called for it to work.

{% code overflow="wrap" lineNumbers="true" %}
```javascript
// We call the function "mySuperFunction" and provide one argument
mySuperFunction(argument);
```
{% endcode %}

## Code

Explore the code below and identify the p5js conditional statement and the variable that is being evaluated to trigger the changes.  Try changing the value of the temperature value and see the results.

#### p5js functions

{% code lineNumbers="true" %}
```javascript
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(0);

  fill("orangered");
  strokeWeight(5);
  stroke("white");
  circle(200, 200, 100);

  fill("deeppink");
  strokeWeight(5);
  stroke("white");
  circle(100, 100, 50);

  fill("aqua");
  strokeWeight(5);
  stroke("white");
  circle(300, 300, 150);

  fill("palegreen");
  strokeWeight(5);
  stroke("white");
  circle(200, 100, 80);
}

```
{% endcode %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Now improved with functions</summary>

{% code overflow="wrap" lineNumbers="true" %}
```javascript
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(0);
  
  // Here we call "my Circle" function four times, and we provide Arguments for the function to process and create the different circles on the screen
  myCircle('orangered', 5, 200, 200, 100);
  myCircle('deeppink', 5, 100, 100, 50);
  myCircle('aqua', 5, 300, 300, 150);
  myCircle('palegreen', 5, 200, 100, 80);
}

// We define the function myCircle.  It takes 5 Parameters, colour, line, x, y and r.  It creates a circle with the desired characteristics.
function myCircle(colour, line, x, y, r){
  fill(colour);
  strokeWeight(line);
  stroke("white");
  circle(x, y, r);
}
```
{% endcode %}

</details>

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Create another function to draw a different shape.
2. Call the function and provide different data to see the results.
3. Add a function to make the shapes move on the canvas.

### Links Projects on p5js&#x20;

* no-function project [**LINK**](https://editor.p5js.org/Garcila/sketches/C7qHnilow)
* function [**LINK**](https://editor.p5js.org/Garcila/sketches/F9nmZPdxD)

### Deep Dive

{% hint style="info" %}
* From p5.js [**LINK**](https://p5js.org/reference/#/p5/function)
* From MDN [**LINK**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)
{% endhint %}
