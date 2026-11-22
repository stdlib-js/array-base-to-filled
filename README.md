<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# toFilled

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return a new array with all elements within a specified range replaced with a provided value.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

To use in Observable,

```javascript
toFilled = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-to-filled@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var toFilled = require( 'path/to/vendor/umd/array-base-to-filled/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-to-filled@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.toFilled;
})();
</script>
```

#### toFilled( x, value, start, end )

Returns a new array with all elements within a specified range replaced with a provided value.

```javascript
var x = [ 1, 2, 3, 4 ];

var out = toFilled( x, 5, 1, 3 );
// returns [ 1, 5, 5, 4 ]

out = toFilled( x, 6, -3, -1 );
// returns [ 1, 6, 6, 4 ]
```

The function accepts the following arguments:

-   **x**: an input array.
-   **value**: fill value.
-   **start**: starting index (inclusive).
-   **end**: ending index (exclusive).

#### toFilled.assign( x, value, start, end, out, stride, offset )

Copies elements from one array to another array and replaces all elements within a specified range with a provided value.

```javascript
var x = [ 1, 2, 3, 4 ];

var out = [ 0, 0, 0, 0 ];
var arr = toFilled.assign( x, 5, 1, 3, out, 1, 0 );
// returns [ 1, 5, 5, 4 ]

var bool = ( arr === out );
// returns true
```

The function accepts the following arguments:

-   **x**: an input array.
-   **value**: fill value.
-   **start**: starting index (inclusive).
-   **end**: ending index (exclusive).
-   **out**: output array.
-   **stride**: output array stride.
-   **offset**: output array offset.

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   Negative indices are resolved relative to the last array element, with the last element corresponding to `-1`.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/random-array-discrete-uniform@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/console-log-each-map@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/utils-nary-function@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/utils-papply@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-to-filled@umd/browser.js"></script>
<script type="text/javascript">
(function () {

// Define an array:
var opts = {
    'dtype': 'generic'
};
var x = discreteUniform( 10, -100, 100, opts );

// Define an array containing random fill values:
var values = discreteUniform( 100, -10000, 10000, opts );

// Define arrays containing random fill ranges:
var starts = discreteUniform( values.length, 0, x.length-1, opts );
var ends = discreteUniform( values.length, 1, x.length, opts );

// Randomly fill ranges of the input array:
logEachMap( 'fill with %d in [%d, %d) => x = [%s]', values, starts, ends, naryFunction( papply( toFilled, x ), 3 ) );

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/array-base-to-filled.svg
[npm-url]: https://npmjs.org/package/@stdlib/array-base-to-filled

[test-image]: https://github.com/stdlib-js/array-base-to-filled/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/array-base-to-filled/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/array-base-to-filled/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/array-base-to-filled?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/array-base-to-filled.svg
[dependencies-url]: https://david-dm.org/stdlib-js/array-base-to-filled/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/array-base-to-filled/tree/deno
[deno-readme]: https://github.com/stdlib-js/array-base-to-filled/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/array-base-to-filled/tree/umd
[umd-readme]: https://github.com/stdlib-js/array-base-to-filled/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/array-base-to-filled/tree/esm
[esm-readme]: https://github.com/stdlib-js/array-base-to-filled/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/array-base-to-filled/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/array-base-to-filled/main/LICENSE

</section>

<!-- /.links -->
