# LearnPack with HTML/CSS

If you want to create an HTML/CSS coding tutorial, you have to use the [`@learnpack/html`](https://www.npmjs.com/package/@learnpack/html) plugin in order to compile and test your exercises. Go to [Compiler Plugins](/configure#compiler-plugins) to see how to install the plugin.

In addition, the main file should be named `index.html`, and the file for the tests, should be named `tests.js`.

### Unit Testing

For testing, you should install [Jest](https://jestjs.io/) with the version "24.8.0". You can install it by running the following command: `npm install jest@24.8.0 -g`

If you are not so familiar with [Jest](https://jestjs.io/), here are the most common tests that you will use when testing an HTML/CSS exercise tutorial:

### Testing a tag exists

```js
// tests.js

const fs = require("fs");
const path = require('path');

const html = fs.readFileSync(path.resolve(__dirname, './index.html'), 'utf8');
test('The <title> tag should exist', () => {
  let tag = document.querySelector("title");
  expect(tag).toBeTruthy();
})
```

### Testing a tag has the expected innerHTML

```js
// tests.js

const fs = require("fs");
const path = require('path');
const html = fs.readFileSync(path.resolve(__dirname, './index.html'), 'utf8');

test('The <title> tag exists and the innerHTML should be "Hello World"', () => {
  let tag = document.querySelector("title");
  expect(tag).toBeTruthy();
  let file = document.documentElement.innerHTML = html.toString();
  expect(tag.innerHTML).toBe("Hello World");
})
```

### Testing a tag has a specific number of children

```js
// tests.js

const fs = require("fs");
const path = require('path');
const html = fs.readFileSync(path.resolve(__dirname, './index.html'), 'utf8');

test('The <ul> tag exists and has three children', () => {
  let tag = document.querySelector("ul");
  expect(tag).toBeTruthy();
  expect(tag.children.length).toBe(3);
})
```

### Testing a tag is inside another tag:[](#testing-a-tag-is-inside-another-tag)

```js
// tests.js

const fs = require("fs");
const path = require('path');
const html = fs.readFileSync(path.resolve(__dirname, './index.html'), 'utf8');

test('The <ul> tag should be inside of the <div>', () => {
  let div = document.querySelector("div");
  expect(div).toBeTruthy();
  let ul = div.querySelector("ul");
  expect(ul).toBeTruthy();
})
```

### Testing the value of a specific property

You can use this example for all the properties, they could be: `src`, `href`, `innerHTML`, `id`, `alt`, etc.

```js
// tests.js

const fs = require("fs");
const path = require('path');
const html = fs.readFileSync(path.resolve(__dirname, './index.html'), 'utf8');

test('The href of the <a> tag should be the expected', () => {
  let a = document.querySelector("a");
  expect(a).toBeTruthy();
  expect(a.href).toBe("https://www.learnpack.co");
})
```

#### Testing a tag has a specific style

```js
// tests.js

const fs = require("fs");
const path = require('path');
const html = fs.readFileSync(path.resolve(__dirname, './index.html'), 'utf8');

test('The <p> tag should have a red font color', () => {
  let p = document.querySelector("p");
  expect(p).toBeTruthy();
  expect(p.style.color).toBe("red");
})
```

### Examples

The following links are HTML and CSS coding tutorials:

*   ​[https://github.com/breatheco-de/exercise-postcard](https://github.com/breatheco-de/exercise-postcard)​
*   ​[https://github.com/4GeeksAcademy/html-tutorial-exercises-course](https://github.com/4GeeksAcademy/html-tutorial-exercises-course)​
*   ​[https://github.com/4GeeksAcademy/css-tutorial-exercises-course](https://github.com/4GeeksAcademy/css-tutorial-exercises-course)​
    

*   ​[https://github.com/4GeeksAcademy/bootstrap-exercises-tutorial](https://github.com/4GeeksAcademy/bootstrap-exercises-tutorial)​
    
