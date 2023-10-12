# LearnPack for DOM Exercises and Tutorials

If you want to create a Javascript/Node coding tutorial, you have to use the [`@learnpack/dom`](https://www.npmjs.com/package/@learnpack/dom) plugin in order to compile and test your exercises. Go to [Compiler Plugins](/configure#compiler-plugins) to see how to install the plugin.

The main file should be named `index.html` and the file for the tests should be named `tests.js`

## Unit Testing

For testing, you should install [Jest](https://jestjs.io/) with version "27.0.6". You can install it by running the following command: `npm install jest@27.0.6 -g`

Besides Jest, you can use [Testing Library](https://testing-library.com/docs/dom-testing-library/intro/) which allows you to create events-related tests. You can check the documentation [here](https://testing-library.com/docs/dom-testing-library/intro/).

The DOM tests are very similar to HTML/CSS tests, except for the events-related tests, which you should use the [Testing Library](https://testing-library.com/docs/dom-testing-library/intro/) for it.

If you are not so familiar with [Jest](https://jestjs.io/) or [Testing Library](https://testing-library.com/docs/dom-testing-library/intro/), here are the most common tests that you will use when testing a DOM exercise tutorial:

### Testing that an HTML tag exists

```js
//tests.js

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
  let tag \= document.querySelector("ul");
  expect(tag).toBeTruthy();
  expect(tag.children.length).toBe(3);
})
```

### Testing a tag is inside another tag

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

#### Testing the value of a specific HTML tag property

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

### Testing a tag has a specific style

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

### Testing something happened after a click

```js
// tests.js

const { queryByText, fireEvent, waitFor} = require('@testing-library/dom');
const fs = require('fs');
const path = require('path');

test('<li> must be added into the <ul> after <button> is clicked', async () => {
  const app = require(path.resolve(__dirname, './index.js'))
  const btn = queryByText(document, 'Click me')
  fireEvent.click(btn)

  let ul = document.querySelector('#myList') // This <ul> has 3 elements already.
  await waitFor(() => expect(ul.childElementCount).toBe(4))
})
```

### Examples

The following links are DOM coding tutorials:
*   ​[https://github.com/4GeeksAcademy/javascript-dom-tutorial-exercises](https://github.com/4GeeksAcademy/javascript-dom-tutorial-exercises)​
*   ​[https://github.com/4GeeksAcademy/javascript-events-tutorial-exercises](https://github.com/4GeeksAcademy/javascript-events-tutorial-exercises)​
