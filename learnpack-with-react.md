# LearnPack with React

If you want to create a Javascript/Node coding tutorial, you have to use the [`@learnpack/react`](https://www.npmjs.com/package/@learnpack/react) plugin in order to compile and test your exercises. Go to [Compiler Plugins](/configure#compiler-plugins) to see how to install the plugin.

In addition, the main file should be named `app.jsx`, and the file for the tests, should be named `tests.js`.

## Unit Testing

For testing, you should install [Jest](https://jestjs.io/) with the version "24.8.0". You can install it by running the following command: `npm install jest@24.8.0 -g`

When testing react exercises, the most common tests are related to the component's structure, you can test that or that the file `app.jsx` have a specific sentence inside.

If you are not so familiar with [Jest](https://jestjs.io/), here are the most common tests that you will use when testing a React exercise tutorial:

### Testing the component has the right structure and tags

```js
// tests.js

import ReactDOM from "react-dom";
import { WhatToRender } from "./app.jsx";
import renderer from "react-test-renderer";

test("The component should return the exact HTML", () => {
  const tree = renderer.create(ReactDOM.render.mock.calls[0][0]).toJSON();
  expect(tree).toMatchInlineSnapshot(`
    <h1>
    Hello
    <strong>
    World!
    </strong>
    </h1>
  `)
})
```

### Testing the file has specific sentences with regular expressions

```js
// tests.js

const fs = require('fs');
const path = require('path');

const app_content = fs.readFileSync(path.resolve(__dirname, './app.jsx'), 'utf8');

test("You should use "{singleAnimal.label}" to get the animal name", () => {
  expect(app_content).toMatch(/{\s*singleAnimal.label\s*}/g);
})
```

### Examples

The following link is a React coding tutorial:

*   ​[https://github.com/4GeeksAcademy/react-tutorial-exercises](https://github.com/4GeeksAcademy/react-tutorial-exercises)​
