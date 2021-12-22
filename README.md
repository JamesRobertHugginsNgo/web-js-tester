# js-tester

Version 4.1.0

Tool for testing JavaScript codes.

## Install

Install the latest version as an NPM dependency.

``` console
npm install https://github.com/JamesRobertHugginsNgo/js-tester.git#4.1.0
```

## Usage

``` JavaScript
// NODEJS
const jsTester = require('js-tester');

// OR

// BROWSER (ES5 OR ES6)
/* global jsTester */

// OR

// BROWSER (ES6 MODULE)
import jsTester from './node_module/js-tester/dist/es6-module/js-tester.js';

```

``` JavaScript
Promise.resolve()
  .then(() => {
    return jsTester('TESTER 1', () => 'DATA')
      .test('TEST PASS', (value) => value === 'DATA')
      .test('TEST FAIL', (value) => value !== 'DATA')
      .promise()
      .then((data) => void console.log(JSON.stringify(data, null, 2)), (error) => void console.error(error));
  })
  .then(jsTester('TESTER 2', () => 'DATA')
    .test('TEST PASS', (value) => value === 'DATA')
    .test('TEST FAIL', (value) => value !== 'DATA')
    .promise)
  .then(jsTester('TESTER 3', (value) => `${value} B`)
    .test('TEST PASS', (value) => value === 'DATA B')
    .test('TEST FAIL', (value) => value !== 'DATA B')
    .promise)
  .then((data) => void console.log(JSON.stringify(data, null, 2)), (error) => void console.error(error));
```
