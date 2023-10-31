# Creative Visualizations

<figure><img src="../.gitbook/assets/spaces_KxBjr6N2JcliQHF5qYum_uploads_yNTV0Q4H4ugKK1YZZaPV_Screen Shot 2023-10-25 at 8.webp" alt=""><figcaption></figcaption></figure>

<figure><img src="broken-reference" alt=""><figcaption><p>World Population as circles</p></figcaption></figure>

### Code

```javascript
let countries;

function preload() {
  countries = loadTable("./countries.csv", "csv", "header");
}

function setup() {
  createCanvas(600, 400);
  background(0);

  for (let i = 0; i < countries.getRowCount(); i++) {
    let diam = countries.getNum(i,'2022 Population');
    
    let mappedDiam = map(diam, 510, 1425887337, 5,50);
    
    circle(random(10, width-10), random(10, height-10), mappedDiam);
  }
}

function draw() {
  
}

```

### p5js Link

{% embed url="https://editor.p5js.org/Garcila/sketches/J1QuqA9e_" %}

***

<figure><img src="../.gitbook/assets/spaces_KxBjr6N2JcliQHF5qYum_uploads_i1q3RbaJ73Pjp0Pr987U_Screen Shot 2023-10-25 at 8.webp" alt=""><figcaption></figcaption></figure>

### Code

```javascript
let countries;
let ang = 0;

function preload() {
  countries = loadTable("countries.csv", "csv", "header");
}

function setup() {
  createCanvas(600, 600);
}

function draw() {
  noStroke();
  translate(300,300);
  background(255);
  // console.log("columns ", countries.getColumn("Country/Territory"));
  console.log("pop", countries.getColumn("2022 Population"));
  console.log("number of rows ", countries.getRowCount());
  console.log("number of columns ", countries.getColumnCount());

  
  for (let i = 0; i < countries.getRowCount(); i++) {
    let diam = countries.getString(i, '2022 Population');
    diam = map(diam, 510, 1425887337, 2, 50);
    let red = map(diam, 2, 50, 200, 255);
    let green = map(diam, 2, 50, 150, 255);
    let blue = map(diam, 2, 50, 250, 255);
    
    fill(red, green, blue);
    
    // circle(random(10,width-10), random(10,height-10), diam);
    let x = cos(ang)*i;
    let y = sin(ang)*i;
    circle(x,y,diam);
    ang +=10;
  }

  noLoop();
}
```

### p5js Link

{% embed url="https://editor.p5js.org/Garcila/sketches/fi0GTgsVZ" %}
