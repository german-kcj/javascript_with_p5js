---
description: If (shark === '🦈'){circle(20,20,20);}
cover: .gitbook/assets/js_with_p5js.png
coverY: 0
---

# Conditionals

<figure><img src=".gitbook/assets/Screen Shot 2023-08-03 at 11.14.41 AM.png" alt=""><figcaption></figcaption></figure>

## Conditionals

These are statements that allow the program to make decisions depending on different conditions that evaluate to true or false.&#x20;

Conditionals are crucial for controlling the flow of your program and executing different sets of code depending on whether the condition is met or not.  In a way, we can say that conditionals add the concept of choice and variety to our application.

The basic conditional statement in JavaScript is the "if" statement.&#x20;

## Code

Explore the code below and identify the p5js conditional statement and the variable that is being evaluated to trigger the changes.  Try changing the value of the temperature value and see the results.

#### p5js conditionals

{% code lineNumbers="true" %}
```javascript
let temperature = -5;

function setup() {
  createCanvas(400, 400);
  background(255);
  textSize(32);
}

function draw() {
 if(temperature < 3){
   background('gray');
   text('It is very cold ☃️', 60, height/2);
 } else if(temperature < 20){
   background('lightblue');
   text('It is quite cool 🌬', 60, height/2);
 } else {
   background('orange');
   text('It is hot 😎', 60, height/2);
 }
}
```
{% endcode %}

#### conditionals and probability

The example below expands the concept of conditionals by introducing probability.  The example is inspired by the historic coding line "10 print" - [LINK](https://10print.org/).  Notice that there are two conditional statements, one decides what line to draw if a / or a \ depending on the value of the variable **randy**, and the other moves the line creation to the next row.

{% code lineNumbers="true" %}
```javascript
let space = 20;
let x = 0;
let y = 0;

function setup() {
  createCanvas(400, 400);
  background(255);
}

function draw() {
  // The function random(), returns a value 
  // between 0 and 1
  let randy = random();

  // This is the equivalent of flipping a coin.  There is
  // 50% chance it will be greater than 0.5 and 50% it
  // will be less or equal than 0.5
  if (randy > 0.5) {
    // Make sure you understand these algorithms to create
    // a / and a \.  Practice using graph paper
    line(x, y, x + space, y + space);
  } else {
    line(x, y + space, x + space, y);
  }
  
  // This conditional statement decides when to draw 
  // on a row or change to the next
  if (x > width) {
    x = 0;
    y = y + space;
  } else {
    x += space;
  }
}
```
{% endcode %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> More involved version- PRINT10</summary>

```javascript
let x = 0;
let y = 0;
let gap = 10;

function setup() {
  createCanvas(windowWidth, windowHeight);
  background(81, 94, 148);
}

function draw() {
  let randy = random(0, 100);
  stroke(255, random(20, 100));
  fill(y, x,150, random(20, 200));

  if (randy < 50) {
    circle(x, y, gap / 2);
    line(x, y, x + gap, y + gap);
  } else {
    fill(255, 5);
    circle(x, y, gap / random(1, 8));

    fill(y, x, 200, random(20, 200));
    circle(x, y, gap / random(1, 8));
    
    fill(x, y, 200, random(20, 200));
    rect(x, y, gap);
    
    strokeWeight(0.2);
    point(x, y);
    line(x, y + gap, x + gap, y);
  }

  if (x > width) {
    y = y + gap;
    x = 0;
  } else {
    x = x + gap;
  }

  if (y > height) {
    y = 0;
  }
}

```

</details>

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Add more shapes, circles, triangles, rectangles and arcs.
2. Add colour to the shapes.
3. Change the size and colour with your space,x and y variables.
4. Make sure that the program stops drawing when the canvas is full.
5. Have the drawing, loop to the top once it reaches the bottom of the canvas, drawing on top of the existing image.

### Links Projects on p5js&#x20;

* 10 Print basic [**LINK**](https://editor.p5js.org/Garcila/sketches/3IziprM9a)
* 10 Print enhanced [**LINK**](https://editor.p5js.org/Garcila/sketches/zQrNDjEcw)

### Deep Dive

{% hint style="info" %}
* From p5.js [**LINK**](https://p5js.org/reference/#/p5/if-else)
* From MDN [**LINK**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
{% endhint %}

<details>

<summary>ChatGPT Code Explanation</summary>

<mark style="color:blue;">**`10 PRINT CHR$(205.5+RND(1)); : GOTO 10`**</mark>, is a short **BASIC** program, often referred to as a one-liner, that generates a simple visual pattern when run on a computer or a device with a BASIC interpreter. Let's break it down:

1. <mark style="color:blue;">**`10`**</mark> is a line number. In older versions of BASIC, line numbers were used to label different sections of the code. In this case, `10` is just an arbitrary line number.
2. <mark style="color:blue;">**`PRINT`**</mark> is a command in BASIC used to display text or values on the screen.
3. <mark style="color:blue;">**`CHR$()`**</mark> is a function in BASIC that converts a numeric value into a character based on the ASCII character set. In this case, it takes the result of the expression `205.5+RND(1)` and converts it into a character.
4. <mark style="color:blue;">**`205.5+RND(1)`**</mark> is an expression that generates a random number between 205.5 and 206.5. <mark style="color:blue;">**`RND(1)`**</mark> generates a random number between 0 and 1, and when you add it to 205.5, you get a random number in the specified range.
5. <mark style="color:blue;">**`;`**</mark> is used to separate multiple PRINT statements on the same line.
6. <mark style="color:blue;">**`GOTO 10`**</mark> is a command that tells the program to jump back to line 10, creating a loop. This means that after printing a character, the program will go back to line 10 and repeat the process indefinitely.

So, what this program does is repeatedly print a character on the screen, and the character it prints is somewhat random because of the `RND(1)` function. It keeps doing this in an infinite loop, creating a continuous pattern on the screen. The specific character printed depends on the random value generated, but it's likely to be a character with an ASCII value between 205 and 206. The visual effect is a constantly changing pattern on the screen, often called a "random walk."

This type of program was popular in the early days of home computing when BASIC was a common programming language for personal computers. It's a simple example of generative art, where randomness is used to create visually interesting patterns.

</details>
