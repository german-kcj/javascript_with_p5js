---
description: let img = loadImage( "./pepito.png" );
cover: ../.gitbook/assets/js_with_p5js.png
coverY: 0
---

# Images

<figure><img src="../.gitbook/assets/Screen Shot 2023-08-03 at 11.18.55 AM.png" alt=""><figcaption></figcaption></figure>

## Images

In p5js we can load and manipulate images to create artistic interpretations or to be used in our projects as sprites or as a way to enhance our content.

## Code

Explore the code below and identify the previously learned concepts.  What is different from the previous examples?  Notice the new elements:

{% code overflow="wrap" lineNumbers="true" %}
```javascript
let img;
let myCanvas;

// preload allows the program to load assets and perform functions before the first-page load
function preload() {
  // We assign the result of the loadImage to the variable img
  img = loadImage(
    "https://th.bing.com/th/id/OIG.aNqD2DLYf_snrEaj01eu?pid=ImgGn"
  );
}

function setup() {
  // We can decide how big we want our image to be
  img.resize(600, 600);

  myCanvas = createCanvas(img.width, img.height);

    // This is the heart of the operation.  We have a nested loop that goes over every column and for each column, it checks every row of pixels in the image.  
    for (let col = 0; col < img.width; col += 1) {
      for (let row = 0; row < img.height; row += 1) {
        // the get function takes an x and y parameters and extracts the r, g, b values from that pixel.
        let colour = img.get(col, row);

        stroke(color(colour));
        point(col, row);
      }
    }
}

// We are not doing the loops within the draw function as the operation will be too computationally intensive.  It may work, but it is likely to slow down the framerate and in this case is not needed
function draw() {
}
```
{% endcode %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Adding noise, black and white, red</summary>

Try this first as the challenges as presented in the **challenge** **list** below and then see how your approach compares to our code.

{% code overflow="wrap" %}
```javascript
let astro;
let myCanvas;

function preload() {
  astro = loadImage("assets/astro.jpeg");
}

function setup() {
  astro.resize(600, 600);

  myCanvas = createCanvas(astro.width, astro.height);

  for (let col = 0; col < astro.width; col += 1) {
    for (let row = 0; row < astro.height; row += 1) {
      let cAstro = astro.get(col, row);

      // Make the image black and white
      // let c = [cAstro[0],cAstro[0],cAstro[0],255];

      // Add noise to the image
      let c = [cAstro[0],cAstro[1],cAstro[2], random(255)];

      // Only show the red channel
      // let c = [cAstro[0],0,0,255];

      stroke(color(c));
      point(col, row);
    }
  }
}

function draw() {}

```
{% endcode %}

</details>

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Image kitchen sink</summary>

We are adding many different options in this example.  Take it one step at a time.

{% code overflow="wrap" %}
```javascript
let img;
let myCanvas;
let squareIt;
let rollIt;
let bendIt;
let original;

let roll = false;
let selected = "none";

function preload() {
  img = loadImage(
    "https://th.bing.com/th/id/OIG.aNqD2DLYf_snrEaj01eu?pid=ImgGn"
  );

}

function setup() {
  frameRate(20);
  img.resize(600, 600);
  myCanvas = createCanvas(img.width, img.height);

  original = createButton("Original");
  original.position(10, img.height + 10);
  original.mousePressed(originalImage);

  squareIt = createButton("Square It");
  squareIt.position(80, img.height + 10);
  squareIt.mousePressed(squareItImage);

  rollIt = createButton("Roll It");
  rollIt.position(160, img.height + 10);
  rollIt.mousePressed(rollItImage);

  bendIt = createButton("Bend It");
  bendIt.position(220, img.height + 10);
  bendIt.mousePressed(bendItImage);

  anime = createButton(roll ? "Stop" : "Animate");
  anime.position(320, img.height + 10);
  anime.mousePressed(animate);

  for (let col = 0; col < img.width; col += 1) {
    for (let row = 0; row < img.height; row += 1) {
      let c = img.get(col, row);
      stroke(color(c));
      point(col, row);
    }
  }
}

function originalImage() {
  background(0);
  for (let col = 0; col < img.width; col += 1) {
    for (let row = 0; row < img.height; row += 1) {
      let c = img.get(col, row);
      stroke(color(c));
      strokeWeight(10);
      point(col, row);
    }
  }
}

function rollItImage() {
  selected = "circle";
  background(0);
  for (let col = 0; col < img.width; col += 10) {
    for (let row = 0; row < img.height; row += 10) {
      let c = img.get(col, row);
      stroke(color(c));
      strokeWeight(2);
      c[3] = random(255); // add alpah
      fill(c);
      ellipse(col, row, random(1, 9));
    }
  }
}

function squareItImage() {
  selected = "cube";
  background(0);
  for (let col = 0; col < img.width; col += 10) {
    for (let row = 0; row < img.height; row += 10) {
      let c = img.get(col, row);
      stroke(color(c));
      strokeWeight(2);
      c[3] = random(255); // add alpah
      fill(c);
      rect(
        col + random(-5, 5),
        row + random(-5, 5),
        random(-10, 10),
        random(-10, 10)
      );
    }
  }
}

function bendItImage() {
  selected = "bend";
  background(0);
  for (let col = 0; col < img.width; col += 10) {
    for (let row = 0; row < img.height; row += 10) {
      let c = img.get(col, row);
      stroke(color(c));
      strokeWeight(random(0, 2));
      c[3] = random(255); // add alpah
      fill(c);
      arc(col, row, random(1, 20), random(1, 20), PI + QUARTER_PI, TWO_PI);
    }
  }
}

function animate() {
  roll = roll === true ? false : true;
  anime.html(roll ? "Stop" : "Animate");
}

function draw() {
  if (roll) {
    switch (selected) {
      case "cube":
        squareItImage();
        break;
      case "circle":
        rollItImage();
        break;
      case "bend":
        bendItImage();
        break;
      default:
        break;
    }
  }
}

function keyPressed() {
  if (key === 's') {
    saveGif('cosmy', 5);
  }
}

```
{% endcode %}

</details>

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Try changing the increment value within the for loops.  Do it one number at a time and see how these changes impact the image.
2. Load an image of your own.
3. How would you display only the red channel of the image? how about black and white?
4. Can you have the image 'glitch' in colour and position of the pixels?
5. Can you add noise?

### Links Projects on p5js&#x20;

* Load and image [**LINK**](https://editor.p5js.org/Garcila/sketches/5owiR0JZD)
* Image colour and noise [**LINK**](https://editor.p5js.org/Garcila/sketches/kkP7kq8BS)
* Kitchen sink [**LINK**](https://editor.p5js.org/Garcila/sketches/bBXZvpDKS)
