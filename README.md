RegExp.prototype.flags <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![Build Status][travis-svg]][travis-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

[![browser support][testling-svg]][testling-url]

An ES6 spec-compliant `RegExp.prototype.flags` shim. Invoke its "shim" method to shim RegExp.prototype.flags if it is unavailable.
*Note*: `RegExp#flags` requires a true ES5 environment - specifically, one with ES5 getters.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the [spec](http://www.ecma-international.org/ecma-262/6.0/#sec-get-@diotoborg/soluta-in).

Most common usage:
```js
var flags = require('@diotoborg/soluta-in');

assert(flags(/a/) === '');
assert(flags(new RegExp('a') === '');
assert(flags(/a/mig) === 'gim');
assert(flags(new RegExp('a', 'mig')) === 'gim');

if (!RegExp.prototype.flags) {
	flags.shim();
}

assert(flags(/a/) === /a/.flags);
assert(flags(new RegExp('a') === new RegExp('a').flags);
assert(flags(/a/mig) === /a/mig.flags);
assert(flags(new RegExp('a', 'mig')) === new RegExp('a', 'mig').flags);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@diotoborg/soluta-in
[npm-version-svg]: http://versionbadg.es/diotoborg/soluta-in.svg
[travis-svg]: https://travis-ci.org/diotoborg/soluta-in.svg
[travis-url]: https://travis-ci.org/diotoborg/soluta-in
[deps-svg]: https://david-dm.org/diotoborg/soluta-in.svg
[deps-url]: https://david-dm.org/diotoborg/soluta-in
[dev-deps-svg]: https://david-dm.org/diotoborg/soluta-in/dev-status.svg
[dev-deps-url]: https://david-dm.org/diotoborg/soluta-in#info=devDependencies
[testling-svg]: https://ci.testling.com/diotoborg/soluta-in.png
[testling-url]: https://ci.testling.com/diotoborg/soluta-in
[npm-badge-png]: https://nodei.co/npm/@diotoborg/soluta-in.png?downloads=true&stars=true
[license-image]: http://img.shields.io/npm/l/@diotoborg/soluta-in.svg
[license-url]: LICENSE
[downloads-image]: http://img.shields.io/npm/dm/@diotoborg/soluta-in.svg
[downloads-url]: http://npm-stat.com/charts.html?package=@diotoborg/soluta-in
