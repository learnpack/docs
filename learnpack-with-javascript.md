
If you want to create a Javascript/Node coding tutorial, you have to use the [`@learnpack/node`](https://www.npmjs.com/package/@learnpack/node) plugin in order to compile and test your exercises. Go to [Compiler Plugins](./configure#compiler-plugins) to see how to install the plugin.

In addition, the main file should be named `app.js` (or you can set the name on the learn.json), and the file for the tests, should be named `tests.js` (you can also set the name on the learn.json).

## Unit Testing

For testing, you should install [Jest](https://jestjs.io/) with the version "24.8.0". You can install it by running the following command: `npm install jest@24.8.0 -g`

If you are not familiar with Jest, here are the most common tests that you will use when testing a Javascript exercise tutorial:

### Testing if a variable exists

```js
//tests.js

// rewirte library is used to avoid using import/export statements on the student code
const rewire = require('rewire');
  
test('The variable "name" should exist', () => {
  const file = rewire("./app.js");
  const name = file.__get__("name");
  expect(name).not.toBe(undefined);
})
```

### Testing a variable has the expected value

```js

// tests.js

const rewire = require('rewire');

test('The variable "name" should have "James" as its value', () => {
  const file = rewire("./app.js");
  const name = file.__get__("name");
  expect(name).toBe("James");
})
```

### Testing a function exists:

```js
// tests.js

const rewire = require('rewire');

test('The function "sum" should exist', () => {
  const file = rewire("./app.js");
  const sum = file.__get__("sum");
  expect(sum).not.toBe(undefined);
})
```

### Testing a function returns the expected value:

```js
// tests.js

const rewire = require('rewire');

test('The function "sum" should return the sum of two numbers', () => {
  const file = rewire("./app.js");
  const sum = file.__get__("sum");
  expect(sum(4, 8)).toBe(12);
})
```

### Testing the file has specific sentence with regular expressions

```js
// tests.js

const fs = require('fs');
const path = require('path');
const rewire = require('rewire');

test('You have to use Math.random() function', () => {
  const file = fs.readFileSync(path.resolve(__dirname, './app.js'), 'utf8');
  const regex = /Math\s*\.\s*random/gm
  expect(regex.test(file.toString())).toBeTruthy();
})
```

### Testing a particular string has been printed in the console

```js
// tests.js

const rewire = require('rewire');
let buffer = "";
global.console.log = console.log = jest.fn((text) => buffer += text + "\n");

test('You have to call console.log() with "Hello World!" as value', () => {
  const file = rewire("./app.js");
  expect(buffer.includes("Hello World!\n")).toBe(true);
})
```

### Testing a function has been called with a specific parameter

```js
// tests.js

const rewire = require('rewire');
global.console.log = console.log = jest.fn(text => null);

test('You have to call console.log() with 50 as value', () => {
  const file = rewire("./app.js");
  expect(console.log).toHaveBeenCalledWith(50);
})
```

### Testing a function has been called a specific number of times

```js
// tests.js

const rewire = require('rewire');
global.console.log = console.log = jest.fn(text => null);

test('You have to call console.log() twice', () => {
  const file = rewire("./app.js");
  expect(console.log.mock.calls.length).toBe(2);
})
```

## Examples

The following links are javascript coding tutorials:

*   ​[https://github.com/4GeeksAcademy/javascript-beginner-exercises-tutorial](https://github.com/4GeeksAcademy/javascript-beginner-exercises-tutorial)​
*   ​[https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial](https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial)​
*   ​[https://github.com/4GeeksAcademy/javascript-functions-exercises-tutorial](https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial)​
    

*   ​[https://github.com/4GeeksAcademy/master-javascript-programming-exercises](https://github.com/4GeeksAcademy/master-javascript-programming-exercises)​
    
