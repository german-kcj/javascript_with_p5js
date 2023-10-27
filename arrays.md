---
description: let animals = ['🦄','🐹','🐼','🐯','🐶'];
cover: .gitbook/assets/js_with_p5js.png
coverY: 0
---

# Arrays

<figure><img src=".gitbook/assets/Screen Shot 2023-08-03 at 11.17.19 AM.png" alt=""><figcaption></figcaption></figure>

## Arrays

Arrays are used to **store** and manage collections of data, such as numbers, strings, or even other arrays or objects. Arrays allow you to group multiple values under a single **variable** and access each value using its index position.

In simpler terms, we can say that arrays are like a **box** with compartments where you can put things. Each compartment is like a spot in the box where you can keep something.  The box can **grow** or **shrink** to let us add or remove items.

## Code

Explore the code below and identify the previously learned concepts.  What is different from the previous examples?  Notice the new elements:

#### Arrays

{% code overflow="wrap" lineNumbers="true" %}
```javascript

// This code creates a list of elements. The list is of length 10, meaning we have 10 elements in the array.
let emojis = ['🦄','👾','🐶','🐰','🐳','🍄','🌍','🍉','🍕','🍭'];

// We access the first element on the emojis array at position zero (0).
let chosen = emojis[0]; // this will make the content of chosen to be '🦄'

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(255);
  
  textSize(200);
  // Look at the reference to see what the textAlign code does!
  textAlign(CENTER, CENTER);
  text(chosen, width/2, height/2);
}

// This function is provided by p5.  It creates an event listener that is enabled when the mouse is clicked.
function mouseClicked(){
  // The floor function removes decimal points from a given number
  let randomIndex = floor(random(emojis.length-1));
  chosen = emojis[randomIndex];
  console.log(randomIndex)
}
```
{% endcode %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Adding and removing elements</summary>

In this example, we use **push** to **add** an element to the end of the emojis array and **pop** to **remove** one element from the end of the array.

{% code overflow="wrap" %}
```javascript
// This code creates a list of elements. The list is of length 5.
const emojis = ['🦄','👾','🐰','🐳','🍄'];

// We access the first element on the emojis array at position zero (0).
let chosen = emojis[0];

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(255);
  
  textAlign(CENTER, CENTER);
  textSize(32);
  // display how many emojis we have in the array
  text('emojis.length = ' + emojis.length,200,50)
  
  textSize(200);
  text(chosen, width/2, height/2);  
}

// This function is provided by p5.  It creates an event listener that is enabled when the mouse is clicked.
function mouseClicked(){
  let randomIndex = floor(random(emojis.length-1));
  chosen = emojis[randomIndex];
  console.log('randomIndex ', randomIndex)
}

function keyPressed(e){
  if(key === 'd'){
    // Adds the dragon emoji to the end of the emojis array
    emojis.push('🐲');
    console.log(emojis);
  }
  if(key === 'x'){
    // Removes the last emoji in the emojis array
    emojis.pop();
    console.log(emojis);
  }
}


```
{% endcode %}

</details>

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Looping over arrays</summary>

Arrays and loops work great together, they help simplify our code. As you can see we are always showing the total number of vehicles in the array by limiting our loop to the array's length.

{% code overflow="wrap" lineNumbers="true" %}
```javascript
let vehicles = ['🚗','🚌','🚑','🚛'];

function setup() {
  createCanvas(400, 400);  
}

function draw() {
  background(255);
  textSize(50);
  // We can access the items in the array by using the [] notation.  We include the position (index) of the item we want. vehicles[0] returns '🚗'
  for(let i = 0; i < vehicles.length; i++){
    text(vehicles[i], i * 50, 200)
  }
}

function keyPressed(){
  if(key === 'a'){
    vehicles.push('🚲');
  }
  if(key === 'd'){
    vehicles.pop();
  }
}
```
{% endcode %}

</details>

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Change the code to have a random emoji added (**push**) to the emojis array when you press the letter '**r'**.  One option is to create a second array with many emojis to choose from.
2. Display **all** the emojis in the emojis array.  What happens when you add or remove an emoji from the array?  How can you make sure you only show the exact number of emojis?
3. There are many other **methods** or functions that arrays have.  Try researching and implementing some of them.  Some examples are, **unshift**, **shift**, **slice** and **reverse**.&#x20;

### Links Projects on p5js&#x20;

* Arrays [**LINK**](https://editor.p5js.org/Garcila/sketches/5E1omtdDD)
* Adding and removing elements [**LINK**](https://editor.p5js.org/Garcila/sketches/\_-S\_GldOa)
* Looping over arrays [**LINK**](https://editor.p5js.org/Garcila/sketches/3atuRWF8t)

### Deep Dive

{% hint style="info" %}
From MDN [**LINK**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array)
{% endhint %}



