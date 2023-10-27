---
description: let response = await fetch(url);
cover: .gitbook/assets/js_with_p5js.png
coverY: 0
---

# APIs - Fetch

<figure><img src=".gitbook/assets/Screen Shot 2023-08-03 at 11.21.03 AM.png" alt=""><figcaption></figcaption></figure>

## Fetch

This function is used to make network requests to retrieve data from a URL, typically from a web server or an API. This is extremely useful for fetching data like JSON files, images, text, or other types of content from remote sources. &#x20;

## Code

Explore the code below and identify the previously learned concepts.  What is different from the previous examples?  Notice the new elements:

#### Fetch

The following code makes a call to the Nasa image API, requesting images from one of the items in the queries array.

{% code overflow="wrap" lineNumbers="true" %}
```javascript
let img;
let queries = ["moon", "sun", "earth", "jupiter", "saturn", "venus", "mars"];

function setup() {
  createCanvas(windowWidth, windowHeight);
  textAlign(CENTER, CENTER);
  textSize(width/20);
}

function draw() {
  background(220);
   
  if(img){
    image(img, 0, 0, width, height); 
  } else {
    text('Click to get an image', width/2, height/2);
  }
}

// We are using async to indicate that the result of this function will
// take some time.  It will work asynchronously.  In our case, it is the fetch function that will take some time for the response with the data to arrive.
async function getImage() { 
  let query = queries[floor(random(queries.length))];
  let url = "https://images-api.nasa.gov/search?q=" + query;
  
  // Since we are in an async function we can use the keyword await to tell the program to wait for the function to finish before assigning the value to the response variable
  let response = await fetch(url);
  
  // Once we receive the information store it in the response variable, we proceed to convert the information to a JSON format
  let data = await response.json();
  
  // We inspect the response and store in the variable images an array of images contained in the data variable (JSON)
  let images = data.collection.items;

  let randy = Math.round(Math.random() * images.length);
  
  // Load one random image from the images array and store it in the img variable to be displayed within the draw function
  img = loadImage(images[randy].links[0].href);
}

function mousePressed() {
  getImage();
}

```
{% endcode %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f60e">😎</span> Fetch with Input</summary>

In this example, we improve the previous code by allowing the user to search for any desired topic.

{% code overflow="wrap" lineNumbers="true" %}
```javascript
let img;

function setup() {
  createCanvas(windowWidth, windowHeight);
  // addFormElement();
  textAlign(CENTER, CENTER);
  textSize(width / 20);
  
  // Create input field for the user to enter the desired query
  input = createInput();
  input.size = 200;
  input.position(0, 0);

  // Create submit button
  // The button will call the getImage function once it is pressed
  button = createButton('Submit');
  button.position(150, 0);
  button.mousePressed(getImage);
}

function draw() {
  background(220);

  // if there is an image to display, display it
  if (img) {
    image(img, 0, 0, width, height);
  }
}

async function getImage() {
  let query = input.value();
  let url = "https://images-api.nasa.gov/search?q=" + query;
  
  // The fetch function is part of JavaScript and in this case it takes a url to get the desired information
  let response = await fetch(url);
 
    let data = await response.json();

    let images = data.collection.items;

    let randy = Math.round(Math.random() * images.length);
    img = loadImage(images[randy].links[0].href);
}
```
{% endcode %}

</details>

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Find another API and implement it in the code.
2. Most APIs will require an API-key for you to make your request.  Look at the API documentation and get some cool information

### Links Projects on p5js&#x20;

* Fetch [**LINK**](https://editor.p5js.org/Garcila/sketches/VhxNZomvG)
* Fetch with input [**LINK**](https://editor.p5js.org/Garcila/sketches/4a5mkfahn)

### Deep Dive

{% hint style="info" %}
From MDN [**LINK**](https://developer.mozilla.org/en-US/docs/Web/API/Fetch\_API/Using\_Fetch)
{% endhint %}
