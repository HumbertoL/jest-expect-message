<div align="center">
<h1>jest-27-expect-message</h1>

🃏🗯

Add custom message to Jest expects (with support for Jest 27+). This is a drop in replacement for `jest-expect-message`.

The original `jest-expect-message` will throw this error when used in newer versions of Jest:
```
"TypeError: matcherResult.message is not a function"
```

If `jest-expect-message` is updated to support Jest 27+, this package will be marked as deprecated.
</div>

<hr />

[![Build Status](https://img.shields.io/travis/mattphillips/jest-expect-message.svg?style=flat-square)](https://travis-ci.org/mattphillips/jest-expect-message)
[![Code Coverage](https://img.shields.io/codecov/c/github/mattphillips/jest-expect-message.svg?style=flat-square)](https://codecov.io/github/mattphillips/jest-expect-message)
[![version](https://img.shields.io/npm/v/jest-expect-message.svg?style=flat-square)](https://www.npmjs.com/package/jest-expect-message)
[![downloads](https://img.shields.io/npm/dm/jest-expect-message.svg?style=flat-square)](http://npm-stat.com/charts.html?package=jest-expect-message&from=2017-09-14)
[![MIT License](https://img.shields.io/npm/l/jest-expect-message.svg?style=flat-square)](https://github.com/mattphillips/jest-expect-message/blob/master/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Roadmap](https://img.shields.io/badge/%F0%9F%93%94-roadmap-CD9523.svg?style=flat-square)](https://github.com/mattphillips/jest-expect-message/blob/master/docs/ROADMAP.md)
[![Examples](https://img.shields.io/badge/%F0%9F%92%A1-examples-ff615b.svg?style=flat-square)](https://github.com/mattphillips/jest-expect-message/blob/master/docs/EXAMPLES.md)

## Problem

In many testing libraries it is possible to supply a custom message for a given expectation, this is currently not
possible in Jest.

For example:

```js
test('returns 2 when adding 1 and 1', () => {
  expect(1 + 1, 'Woah this should be 2!').toBe(3);
});
```

This will throw the following error in Jest:

```sh
Expect takes at most one argument.
```

## Solution

`jest-27-expect-message` allows you to call `expect` with a second argument of a `String` message.

For example the same test as above:

```js
test('returns 2 when adding 1 and 1', () => {
  expect(1 + 1, 'Woah this should be 2!').toBe(3);
});
```

With `jest-27-expect-message` this will fail with your custom error message:

```sh
  ● returns 2 when adding 1 and 1

    Custom message:
      Woah this should be 2!

    expect(received).toBe(expected) // Object.is equality

    Expected: 3
    Received: 2
```

## Installation

With npm:
```sh
npm install --save-dev jest-27-expect-message
```

With yarn:
```sh
yarn add -D jest-27-expect-message
```

## Setup

Add `jest-27-expect-message` to your Jest `setupFilesAfterEnv` configuration.
[See for help](https://jestjs.io/docs/en/next/configuration#setupfilesafterenv-array)

### Jest v24+

```json
"jest": {
  "setupFilesAfterEnv": ["jest-27-expect-message"]
}
```

### Jest v23-

```json
"jest": {
  "setupTestFrameworkScriptFile": "jest-27-expect-message"
}
```

## Usage

 - `expect(actual, message)`
   - `actual`: The value you would normally pass into an `expect` to assert against with a given matcher.
   - `message`: String, the custom message you want to be printed should the `expect` fail.

```js
test('returns 2 when adding 1 and 1', () => {
  expect(1 + 1, 'Woah this should be 2!').toBe(3);
});
```

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->
| [<img src="https://avatars0.githubusercontent.com/u/5610087?v=4" width="100px;"/><br /><sub><b>Matt Phillips</b></sub>](http://mattphillips.io)<br />[💻](https://github.com/mattphillips/jest-expect-message/commits?author=mattphillips "Code") [📖](https://github.com/mattphillips/jest-expect-message/commits?author=mattphillips "Documentation") [💡](#example-mattphillips "Examples") [🤔](#ideas-mattphillips "Ideas, Planning, & Feedback") [🚇](#infra-mattphillips "Infrastructure (Hosting, Build-Tools, etc)") [⚠️](https://github.com/mattphillips/jest-expect-message/commits?author=mattphillips "Tests") [🔧](#tool-mattphillips "Tools") |
| :---: |
<!-- ALL-CONTRIBUTORS-LIST:END -->

## LICENSE

[MIT](/LICENSE)

