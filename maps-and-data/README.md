---
cover: ../.gitbook/assets/js_with_p5js.png
coverY: 0
---

# Maps and Data

Today we went over tables, csv and getting data into our program, so that we can manipulate it with JavaScript.  We are on our way to create some cool data visualizations, starting with a bar-chart

<figure><img src="../.gitbook/assets/spaces_KxBjr6N2JcliQHF5qYum_uploads_cWxWa927MuF5AqsHPd5C_Screen Shot 2023-10-25 at 8.webp" alt=""><figcaption></figcaption></figure>

### Code

```javascript
let grades;

function preload() {
  grades = loadTable("./grades.csv", "csv", "header");
}

function setup() {
  createCanvas(400, 400);
  strokeWeight(45);
  strokeCap(SQUARE);
}

function draw() {
  background(0);
  
  for (let row = 0; row < grades.getRowCount(); row++) {
    for (let col = 0; col < grades.getColumnCount(); col++) {
      
      let x = 100 + row * 50;
      let grade = grades.getNum(row, "Grade");
      
      let green = map(grade, 0,100, 0, 255);
      strokeWeight(45);
      stroke(100,green,0);
      
      // optional way to visualize
      // line(x, grade, x, 0); 
      
      line(x, 250-grade, x, 250);
      strokeWeight(2);
      text(grade, x-5, 240 - grade);
      
      stroke(255);
      
      text(grades.getString(row, "Name"), x-5, 300 );
      
    }
  }
  noLoop();
}


```

### p5js Link

{% embed url="https://editor.p5js.org/Garcila/sketches/7vBohELSj" %}

### CSV file

{% file src="../.gitbook/assets/grades (1).csv" %}

In the next page we are playing with the information and displaying it in creative ways.
