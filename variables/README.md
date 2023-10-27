---
description: let shark = '🐳';
cover: ../.gitbook/assets/js_with_p5js.png
coverY: 0
---

# Variables

<figure><img src="../.gitbook/assets/Screen Shot 2023-08-03 at 11.13.20 AM.png" alt=""><figcaption></figcaption></figure>

## Variables in Code

In JavaScript, variables are containers used to store data values. They act as placeholders for various types of information.  Variables provide a way to keep track of and manipulate data during the execution of a program.

To define (or declare) a variable in JavaScript, you use the **var**, **let**, or **const** keyword, followed by the variable name. During these sessions, we'll work with the keyword **let**.

## Code

Explore the code below and identify the p5js variable that contains the value of the current position on the X-axis of the mouse in the canvas.

#### p5js variables

{% code lineNumbers="true" %}
```javascript
function setup() {
  createCanvas(300, 300);
  background(19, 211, 214);
}

function draw() {
  fill(250, 250, 0);
  /* mouseX and mouseY are some of the variables
   provided by p5
   */
   circle(mouseX, 150, 30);
}
```
{% endcode %}

#### User-created variables

The example below contains one variable created by the user, the variable **positionX**. It contains the number 150 and it is used on line 11 to **create** a circle and on line 13 to **update** the circle position each time the function draw runs.

{% code lineNumbers="true" %}
```javascript
let positionX = 150;

function setup() {
  createCanvas(300, 300);
  background(19, 211, 214);
}

function draw() {
  stroke(0);
  fill(250, 250, 0);
  circle(positionX, 150, 20);

  positionX = positionX + random(-5, 5);
}
```
{% endcode %}

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Make the circle also move randomly on the y-axis.
2. Make the circle not leave a trace as it moves.
3. Make the circle leave a faint trace
4. Change the colour of the circle and the background.
5. Add a second circle.
6. Mover the circle with your mouse on the X and Y axis.
7. Draw a different shape.

### Links Projects on p5js&#x20;

Variables [**LINK**](https://editor.p5js.org/Garcila/sketches/9T\_99BYYF)

### Deep Dive

{% hint style="info" %}
From MDN [**LINK**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)
{% endhint %}



