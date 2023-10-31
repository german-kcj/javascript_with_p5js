---
description: loadTable('/data/world_pop.csv', 'csv', 'header');
cover: ../.gitbook/assets/js_with_p5js.png
coverY: 0
---

# Leaflet - Mappa - p5js

<figure><img src="../.gitbook/assets/Screen Shot 2023-08-03 at 11.19.51 AM.png" alt=""><figcaption></figcaption></figure>

## Map

**Mappa** is a JavaScript library that works with p5.js to simplify the process of creating interactive maps and geospatial visualizations. It provides a set of tools for working with maps, markers, geolocation, and more.

See root example [**LINK**](https://mappa.js.org/docs/examples-leaflet.html)

## Data

CSV stands for "Comma-Separated Values." It's a simple and widely used file format for storing and exchanging tabular data, where each row of data is represented as a line of text, and the values within a row are separated by commas or other specified delimiters. CSV files are plain text files, making them easy to create, edit, and work with using a variety of software tools.

In a CSV file:

Each line typically represents a row of data. Each value within a row is separated by a comma (,), semicolon (;), or another specified delimiter. The first row often contains headers that describe the contents of each column.

## Code

Explore the code below and identify the previously learned concepts.  What is different from the previous examples?  Notice the new elements:

{% code overflow="wrap" lineNumbers="true" %}
```javascript
// Options for our map
let options = {
  lat: 0,
  lng: 0,
  zoom: 2,
  style: 'http://{s}.tile.osm.org/{z}/{x}/{y}.png'
}

// Create an instance of Leaflet
let mappa = new Mappa('Leaflet');
let myMap;

let canvas;
let countries;

function setup() {
  canvas = createCanvas(800, 700);

  // Create a tile map and overlay the canvas on top.
  myMap = mappa.tileMap(options);
  myMap.overlay(canvas);

  // Load the data
    countries = loadTable('/data/world_pop.csv', 'csv', 'header');

  fill(70, 203,31);	
  stroke(100);
}

function draw() {
  drawPopulation()
}

function drawPopulation() {
  // Clear the canvas
  clear();

  for (let i = 0; i < countries.getRowCount(); i++) {
    // Get the lat/lng of each country 
    let latitude = Number(countries.getString(i, 'latitude'));
    let longitude = Number(countries.getString(i, 'longitude'));
    let name = countries.getString(i, 'Country/Territory');
    let pop = countries.getString(i, '2022 Population');

    // Only draw them if the position is inside the current map bounds. We use a
    // Leaflet method to check if the lat and lng are contain inside the current
    // map. This way we draw just what we are going to see and not everything. See
    // getBounds() in http://leafletjs.com/reference-1.1.0.html
    if (myMap.map.getBounds().contains({lat: latitude, lng: longitude})) {
      
      // Transform lat/lng to pixel position
      let pos = myMap.latLngToPixel(latitude, longitude);
      
      // Get the size of the population and map it.
      let size = countries.getString(i, '2022 Population');
      
      size = map(size, 510, 1425887337, 2, 50) + myMap.zoom();
      
      fill(250,0,250)
      ellipse(pos.x, pos.y, size, size);
      let d = dist(pos.x, pos.y, mouseX, mouseY);
      if(d < 5){
        let num = new Intl.NumberFormat('en-IN', { maximumSignificantDigits: 3 }).format(pop);
        stroke(0);
        fill(0);
        text(name, pos.x+10, pos.y);
        text(num, pos.x+10, pos.y+20);
        
      }
    }
  }
}
```
{% endcode %}

## Challenges

Each day will include several challenges to support your learning.  Make use of any of the following tools to help you in the process: Google the question, use the reference material in p5js ask a friend!

1. Change the colour of each circle.
2. Change each circle with another shape.
3. Make different shapes depending on the size of the population.
4. Have different colours representing different population sizes.
5. Look at the world\_pop.csv and find other data you may want to include in the map.
6. Find a different CSV dataset and create your own map.

### Links Projects on p5js&#x20;

* Population mat [**LINK**](https://editor.p5js.org/Garcila/sketches/yOWjPW5fG)
