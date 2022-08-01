<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

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

# Entropy

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> [Triangular][triangular-distribution] distribution [differential entropy][entropy].

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

The [differential entropy][entropy] (in [nats][nats]) for a [triangular][triangular-distribution] random variable with lower limit `a`, upper limit `b`, and mode `c` is 

<!-- <equation class="equation" label="eq:triangular_entropy" align="center" raw="h\left( X \right) = \frac{1}{2} + \ln \left({\frac{b-a}{2}}\right)" alt="Differential entropy for a triangular distribution."> -->

<div class="equation" align="center" data-raw-text="h\left( X \right) = \frac{1}{2} + \ln \left({\frac{b-a}{2}}\right)" data-equation="eq:triangular_entropy">
    <img src="https://cdn.jsdelivr.net/gh/stdlib-js/stdlib@556e0ebc42f54244079cecc91c0883bb6c442244/lib/node_modules/@stdlib/stats/base/dists/triangular/entropy/docs/img/equation_triangular_entropy.svg" alt="Differential entropy for a triangular distribution.">
    <br>
</div>

<!-- </equation> -->

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import entropy from 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-base-dists-triangular-entropy@deno/mod.js';
```

#### entropy( a, b, c )

Returns the [differential entropy][entropy] of a [triangular][triangular-distribution] distribution with minimum support `a`, maximum support`b`, and mode `c` (in [nats][nats]).

```javascript
var v = entropy( 0.0, 1.0, 0.8 );
// returns ~-0.193

v = entropy( 4.0, 12.0, 5.0 );
// returns ~1.886

v = entropy( 2.0, 8.0, 5.0 );
// returns ~1.599
```

If provided `NaN` as any argument, the function returns `NaN`.

```javascript
var v = entropy( NaN, 4.0, 2.0 );
// returns NaN

v = entropy( 0.0, NaN, 2.0 );
// returns NaN

v = entropy( 0.0, 4.0, NaN );
// returns NaN
```

If provided parameters not satisfying `a <= c <= b`, the function returns `NaN`.

```javascript
var y = entropy( 1.0, 0.0, 1.5 );
// returns NaN

y = entropy( 0.0, 1.0, -1.0 );
// returns NaN

y = entropy( 0.0, -1.0, 0.5 );
// returns NaN
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import randu from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-base-randu@deno/mod.js';
import entropy from 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-base-dists-triangular-entropy@deno/mod.js';

var a;
var b;
var c;
var v;
var i;

for ( i = 0; i < 10; i++ ) {
    a = ( randu()*10.0 );
    b = ( randu()*10.0 ) + a;
    c = ( randu()*( b-a ) ) + a;
    v = entropy( a, b, c );
    console.log( 'a: %d, b: %d, c: %d, h(X;a,b,c): %d', a.toFixed( 4 ), b.toFixed( 4 ), c.toFixed( 4 ), v.toFixed( 4 ) );
}
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

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2022. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/stats-base-dists-triangular-entropy.svg
[npm-url]: https://npmjs.org/package/@stdlib/stats-base-dists-triangular-entropy

[test-image]: https://github.com/stdlib-js/stats-base-dists-triangular-entropy/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/stats-base-dists-triangular-entropy/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/stats-base-dists-triangular-entropy/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/stats-base-dists-triangular-entropy?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/stats-base-dists-triangular-entropy.svg
[dependencies-url]: https://david-dm.org/stdlib-js/stats-base-dists-triangular-entropy/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/stats-base-dists-triangular-entropy/tree/deno
[umd-url]: https://github.com/stdlib-js/stats-base-dists-triangular-entropy/tree/umd
[esm-url]: https://github.com/stdlib-js/stats-base-dists-triangular-entropy/tree/esm
[branches-url]: https://github.com/stdlib-js/stats-base-dists-triangular-entropy/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/stats-base-dists-triangular-entropy/main/LICENSE

[triangular-distribution]: https://en.wikipedia.org/wiki/Triangular_distribution

[entropy]: https://en.wikipedia.org/wiki/Entropy_%28information_theory%29

[nats]: https://en.wikipedia.org/wiki/Nat_%28unit%29

</section>

<!-- /.links -->
