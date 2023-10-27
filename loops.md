---
description: for(let i = 0; i < 5; i++){}
cover: .gitbook/assets/js_with_p5js.png
coverY: 0
---

# Loops

<figure><img src=".gitbook/assets/Screen Shot 2023-08-03 at 11.16.21 AM.png" alt=""><figcaption></figcaption></figure>

## Loops

Loops let the computer do something over and over without having to individually write each instruction.  They are like a repetitive game plan for your computer.  It's great for when you want to draw patterns, move things around, or repeat tasks.

There are different types of loops in JavaScript, such as **while** loops, **for** loops and **for** **of** loops.  We'll focus on the traditional **for** loop.

## Code

Explore the code below and identify the previously learned concepts.  What is different from the previous examples?  Notice the new elements:

#### for loop

{% code overflow="wrap" lineNumbers="true" %}
```javascript
function setup() {
  createCanvas(400, 400);  
}

function draw() {
  // We are using the function noLoop to stop the animation
  // It helps to visualize the outcome
  noLoop();
  background(255);
  
  // code to create 5 bubbles without a for loop
  circle(random(width), random(height), 50);
  circle(random(width), random(height), 50);
  circle(random(width), random(height), 50);
  circle(random(width), random(height), 50);
  circle(random(width), random(height), 50);
  
  // generating the 5 bubbles with a for loop
  for(let i = 0; i < 5; i++){
    // We are making these bubbles pink
    fill(250,0,150);
    circle(random(width), random(height), 50);
  }
}
```
{% endcode %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Using the variable 'i' in our for loop</summary>

When we write a for loop, we have access to the variable we are creating, in our case the variable **'i'**.  This variable can be named anything we want, and it can be used within the for loop as illustrated below.&#x20;

{% code overflow="wrap" %}
```javascript
function setup() {
  createCanvas(400, 400);  
}

function draw() {
  noLoop();
  background(255);
  // Do not display the inside of the bubble to better visualize all the bubbles
  noFill();
  
  // generating the 5 bubbles with a for loop
  for(let i = 0; i < 5; i++){
    // We have access to the value in the variable 'i' each round
    //, In this case, we are using the variable 'i' to change the size of the bubble
    stroke(250,0,150);
    circle(random(width), random(height), 50 * i);
  }
}
```
{% endcode %}

</details>

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Comment out the **noLoop()** function. What happens?
2. Use the loop to create 100 bubbles
3. Create another shape, maybe a triangle or rectangle
4. :sunglasses: Use the variable 'i' in different ways:
   1. Change the red, green and blue stroke values.
   2. Add a fill colour and change the transparency (alpha channel).
   3. Arrange the bubbles using 'i 'as part of the x and y coordinates.

### Links Projects on p5js&#x20;

* for loop [**LINK**](https://editor.p5js.org/Garcila/sketches/Ih8cEDwGi)
* Use variable i in loop [**LINK**](https://editor.p5js.org/Garcila/sketches/zo44W5c7f)

### Deep Dive

{% hint style="info" %}
* From p5.js [**LINK**](https://p5js.org/reference/#/p5/for)
* From MDN [**LINK**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
{% endhint %}
