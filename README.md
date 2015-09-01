objnest
==========

<!-- Badge Start -->
<a name="badges"></a>

[![Build Status][bd_travis_shield_url]][bd_travis_url]
[![Code Climate][bd_codeclimate_shield_url]][bd_codeclimate_url]
[![Code Coverage][bd_codeclimate_coverage_shield_url]][bd_codeclimate_url]
[![npm Version][bd_npm_shield_url]][bd_npm_url]
[![bower version][bd_bower_badge_url]][bd_repo_url]

[bd_repo_url]: https://github.com/okunishinishi/node-objnest
[bd_travis_url]: http://travis-ci.org/okunishinishi/node-objnest
[bd_travis_shield_url]: http://img.shields.io/travis/okunishinishi/node-objnest.svg?style=flat
[bd_license_url]: https://github.com/okunishinishi/node-objnest/blob/master/LICENSE
[bd_codeclimate_url]: http://codeclimate.com/github/okunishinishi/node-objnest
[bd_codeclimate_shield_url]: http://img.shields.io/codeclimate/github/okunishinishi/node-objnest.svg?style=flat
[bd_codeclimate_coverage_shield_url]: http://img.shields.io/codeclimate/coverage/github/okunishinishi/node-objnest.svg?style=flat
[bd_gemnasium_url]: https://gemnasium.com/okunishinishi/node-objnest
[bd_gemnasium_shield_url]: https://gemnasium.com/okunishinishi/node-objnest.svg
[bd_npm_url]: http://www.npmjs.org/package/objnest
[bd_npm_shield_url]: http://img.shields.io/npm/v/objnest.svg?style=flat
[bd_bower_badge_url]: https://img.shields.io/bower/v/objnest.svg?style=flat

<!-- Badge End -->


<!-- Description Start -->
<a name="description"></a>

Convert nested object to flatten or expand.

<!-- Description End -->




<!-- Sections Start -->
<a name="sections"></a>

<!-- Section from "docs/readme/01.Installation.md.hbs" Start -->

<a name="section-docs-readme-01-installation-md"></a>
Installation
-----

```bash
npm install objnest --save
```
<!-- Section from "docs/readme/01.Installation.md.hbs" End -->

<!-- Section from "docs/readme/02.Usage.md.hbs" Start -->

<a name="section-docs-readme-02-usage-md"></a>
Usage
-----

**Flatten Object Properties**

Convert nested object into flatten structure.

```javascript
var objnest = require('objnest');
var flattened = objnest.flatten({
    'foo': {'bar': 'baz'}
});
console.log(flattened); // => {'foo.bar': 'baz'}
```

**Expand Object Properties**

Convert flattened object into nested structure.

```javascript
var objnest = require('objnest');
var expanded = objnest.expand({
    'foo.bar': 'baz'
});
console.log(expanded); // => {foo: {bar: 'baz'}}
```
<!-- Section from "docs/readme/02.Usage.md.hbs" End -->

<!-- Section from "docs/readme/03.Tips.md.hbs" Start -->

<a name="section-docs-readme-03-tips-md"></a>
Tips
----


### Handling Array

Brackets with numbers are parsed as array.

```javascript
var objnest = require('objnest');
var flattened = objnest.flatten({
    'foo': {'bar': ['baz0', 'baz1']}
});
console.log(flattened); // => {'foo.bar[0]': 'baz0', 'foo.bar[1]': 'baz1'}
```

```javascript
var objnest = require('objnest');
var expanded = objnest.expand({
    'foo.bar[0]': 'baz0',
    'foo.bar[1]': 'baz1'
});
console.log(expanded); // => {foo: bar:['baz0', 'baz1']}}
```
<!-- Section from "docs/readme/03.Tips.md.hbs" End -->


<!-- Sections Start -->


<!-- LICENSE Start -->
<a name="license"></a>

License
-------
This software is released under the [MIT License](https://github.com/okunishinishi/node-objnest/blob/master/LICENSE).

<!-- LICENSE End -->


