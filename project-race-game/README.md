---
description: if (key === 'g'){if(pinkX < 550 - diam/2){noLoop();}
cover: ../.gitbook/assets/js_with_p5js.png
coverY: 0
---

# Project - Race Game

<figure><img src="../.gitbook/assets/Screen Shot 2023-08-03 at 11.15.33 AM.png" alt=""><figcaption></figcaption></figure>

## Variables, Conditionals and Events

This project is a good recap of all the elements we have learned so far and group them in a racing game.

## Code

Explore the code below and identify the previously learned concepts.  What is different from the previous examples?  Notice the new elements:

#### p5js Basic Race Game

{% code lineNumbers="true" %}
```javascript
let whiteX = 35;
let greenX = 35;
let yellowX = 35;

function setup() {
  createCanvas(400, 200);
}

function draw() {
  background(3, 157, 252);
  noStroke();
  
  // RACING TRACK
  // start rectangle
  fill(252, 123, 3);
  rect(0, 0, 50, 200);

  // end rectangle
  fill(252, 3, 148);
  rect(400 - 50, 0, 50, 200);

  // PLAYERS
  // WHITE
  fill(255, 255, 255);
  circle(whiteX, 100, 20);

  // move white to the right
  whiteX = whiteX + random(5);

  // when white gets to the end, message and stop
  if (whiteX > 400 - 50) {
    text("white wins!", 150, 100);
    noLoop();
  }
  
  // GREEN
  fill(0,220,0);
  circle(greenX, 50, 20);
  greenX = greenX + random(5);
  if(greenX > 350){
    text('green wins!', 150, 100);
    noLoop();
  }
  
  // YELLOW
    fill(255,255,0);
  circle(yellowX, 150, 20);
  yellowX = yellowX + random(5);
  if(yellowX > 350){
    text('yellow wins!', 150, 100);
    noLoop();
  }
}
```
{% endcode %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Race Game Evolved (multiplayer)</summary>

This version of the game makes use of Events.  Actions detected by the computer, in this case by the user pressing keys to make the objects move on the track

```javascript
let pinkX = 25;
let silverX = 25;
let whiteX = 25;
let pinkWin,
  silverWin,
  whiteWin = false;
let diam = 40;

function setup() {
  createCanvas(600, 400);
}

function draw() {
  background(42, 20);
  noStroke();

  // RACETRACK
  fill(0, 20);
  rect(0, 0, 50, 400);

  fill(200, 20);
  rect(550, 0, 50, 400);

  // Silver Player
  fill("silver");
  circle(silverX, 100, 40);
  if (silverWin) {
    text("Silver Wins!", 300, 200);
  }
  
  // Pink Player
  fill("hotpink");
  circle(pinkX, 200, 40);
  if (pinkWin) {
    text("Pink Wins!", 300, 200);
  }

  // White Player
  fill("white");
  circle(whiteX, 300, 40);
  if (whiteWin) {
    text("White Wins!", 300, 200);
  }
}

// Event listener 
// Function that detects the user pressing Keys
function keyPressed() {
  if (key === "a") {
    if (silverX < 550 - diam / 2) {
      silverX += random(-5, 30);
    } else {
      silverWin = true;
      noLoop();
    }
  }
  
  if (key === "g") {
    if (pinkX < 550 - diam / 2) {
      pinkX += random(-5, 30);
    } else {
      pinkWin = true;
      noLoop();
    }
  }

  if (key === "l") {
    if (whiteX < 550 - diam / 2) {
      whiteX += random(-5, 30);
    } else {
      whiteWin = true;
      noLoop();
    }
  }
}
```

</details>

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Race Game with Object Literals  </summary>

```javascript
// Object Literal per player
let whitePlayer = {
  x: 35,
  y: 100,
  diam: 20
}

let greenPlayer = {
  x: 35,
  y: 50,
  diam: 20
}

let yellowPlayer = {
  x: 35,
  y: 150,
  diam: 20
}

function setup() {
  createCanvas(400, 200);
}

function draw() {
  background(3, 157, 252);
  noStroke();
  
  // RACING TRACK
  // start rectangle
  fill(252, 123, 3);
  rect(0, 0, 50, 200);

  // end rectangle
  fill(252, 3, 148);
  rect(400 - 50, 0, 50, 200);

  // PLAYERS
  // WHITE
  fill(255, 255, 255);
  circle(whitePlayer.x, whitePlayer.y, whitePlayer.diam);

  // move white to the right
  whitePlayer.x = whitePlayer.x + random(5);

  // when white gets to the end, message and stop
  if (whitePlayer.x > 400 - 50) {
    text("white wins!", 150, 100);
    noLoop();
  }
  
  // GREEN
  fill(0,220,0);
  circle(greenPlayer.x, greenPlayer.y, greenPlayer.diam);
  greenPlayer.x = greenPlayer.x + random(5);
  if(greenPlayer.x > 350){
    text('green wins!', 150, 100);
    noLoop();
  }
  
  // YELLOW
    fill(255,255,0);
  circle(yellowPlayer.x, yellowPlayer.y, yellowPlayer.diam);
  yellowPlayer.x = yellowPlayer.x + random(5);
  if(yellowPlayer.x > 350){
    text('yellow wins!', 150, 100);
    noLoop();
  }
}
```

</details>

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Change the shape of the participants.  Try having different shapes for each player. What changes do you need to make to keep the game playing the same way?
2. Try changing the shapes with emojis.
3. Use conditionals to add a **surprise** along the track.  Make the surprise a **power-up** to speed up the player, or a **trap** to slow it down.
4. Make the colour of the background change as the players progress in the race.
5. Make the players leave a trail behind them as they race.
6. Add a secret **key-code** to give extra speed to a player.

### Links Projects on p5js&#x20;

* Race basic [**LINK**](https://editor.p5js.org/Garcila/sketches/2rB3BHS6C)
* Race with user input [**LINK**](https://editor.p5js.org/Garcila/sketches/OxblFvkfz)
