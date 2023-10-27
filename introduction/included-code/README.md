---
description: Default code in the p5js editor
cover: ../../.gitbook/assets/js_with_p5js.png
coverY: 0
---

# Included Code

<pre class="language-javascript" data-line-numbers><code class="lang-javascript">function setup() { //happens once at the start
<strong>  createCanvas(400, 400);
</strong>}​
function draw() {
  background(200);
}
</code></pre>

## Current code on the editor <a href="#current-code-on-the-editor" id="current-code-on-the-editor"></a>

As you can see on the code above as part of the original code, there is already some text in the sketch.js area on the editor. In this section, we'll explain what those lines mean.

### setup <a href="#setup" id="setup"></a>

{% code lineNumbers="true" %}
```javascript
function setup() {
  // code goes here
}
```
{% endcode %}

The setup function is in charge of running any code that needs to be executed at the start of the application.

{% hint style="info" %}
​[Click here for a deeper dive on **setup**](https://p5js.org/reference/#/p5/setup)
{% endhint %}

### draw <a href="#draw" id="draw"></a>

```javascript
function draw() {
  // code goes here
}
```

The draw function is in charge of running all code within it over and over again. It works as an infinite loop, meaning that it will repeat for as long as the application is running.

{% hint style="info" %}
[Click here for a deeper dive on **draw**](https://p5js.org/reference/#/p5/draw)**​**​**​**​
{% endhint %}

<details>

<summary>🍎Teacher's Corner - Functions​</summary>

We'll go over this concept later, but here is an introduction:

A function is a sequence of commands that can be reused together later in a program. [source](http://support.kodable.com/en/articles/417313-what-are-functions).

Example:

We can **create (define)** a function named 'brushYourTeeth'.  This function will go over the steps required to brush someone's teeth as seen in the code below &#x20;

{% code lineNumbers="true" %}
```javascript
// define brushYourTeeth function

function brushYourTeeth(){
  // get toothbrush
  // get toothpaste
  // put toothpaste on toothbrush
  // put toothbrush in your mouth
  // clean each tooth with the toothbrush
  // ...
}
```
{% endcode %}

Every time we need to brush teeth, we run **(call or execute)** the function.

{% code lineNumbers="true" %}
```javascript
// call the brushYourTeeth function
brushYourTeeth();
```
{% endcode %}

Functions can receive information in the form of **parameters**.  See parameters [here](https://developer.mozilla.org/en-US/docs/Glossary/Parameter).

</details>

We went over our first lines of code. Now we'll explore what do **CreateCanvas and Background** mean.&#x20;
