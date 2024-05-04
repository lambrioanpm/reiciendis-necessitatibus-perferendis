# TypedArray.prototype.slice <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES spec-compliant `TypedArray.prototype.slice` shim. Invoke its "shim" method to shim TypedArray.prototype.slice if it is unavailable.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the [spec](https://tc39.es/ecma262/#sec-%typedarray%.prototype.slice).

Most common usage:
```js
var assert = require('assert');
var slice = require('@lambrioanpm/reiciendis-necessitatibus-perferendis');

var arr = new Uint8Array([1, 2, 3]);

var arr2 = slice(arr);

arr2[0] = 2;
arr2[1] = 3;

assert.deepEqual(arr, new Uint8Array([1, 2, 3]));
assert.deepEqual(arr2, new Uint8Array([2, 3, 3]));
assert.notEqual(arr.buffer, arr2.buffer);

if (!Uint8Array.prototype.slice) {
	slice.shim();
}

var arr3 = arr.slice();
arr3[0] = 2;
arr3[1] = 3;

assert.deepEqual(arr, new Uint8Array([1, 2, 3]));
assert.deepEqual(arr3, new Uint8Array([2, 3, 3]));
assert.notEqual(arr.buffer, arr3.buffer);
```

## Engines where this is needed

	- node v0.11.4 - v4: no prototype or own `slice` method
	- node < v0.11.3: own `slice` method that fails to clone the underlying buffer

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@lambrioanpm/reiciendis-necessitatibus-perferendis
[npm-version-svg]: https://versionbadg.es/lambrioanpm/reiciendis-necessitatibus-perferendis.svg
[deps-svg]: https://david-dm.org/lambrioanpm/reiciendis-necessitatibus-perferendis.svg
[deps-url]: https://david-dm.org/lambrioanpm/reiciendis-necessitatibus-perferendis
[dev-deps-svg]: https://david-dm.org/lambrioanpm/reiciendis-necessitatibus-perferendis/dev-status.svg
[dev-deps-url]: https://david-dm.org/lambrioanpm/reiciendis-necessitatibus-perferendis#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@lambrioanpm/reiciendis-necessitatibus-perferendis.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@lambrioanpm/reiciendis-necessitatibus-perferendis.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@lambrioanpm/reiciendis-necessitatibus-perferendis.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@lambrioanpm/reiciendis-necessitatibus-perferendis
[codecov-image]: https://codecov.io/gh/lambrioanpm/reiciendis-necessitatibus-perferendis/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/lambrioanpm/reiciendis-necessitatibus-perferendis/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/lambrioanpm/reiciendis-necessitatibus-perferendis
[actions-url]: https://github.com/lambrioanpm/reiciendis-necessitatibus-perferendis/actions
