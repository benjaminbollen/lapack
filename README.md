# LAPACK [![Version][version-img]][version-url] [![Status][status-img]][status-url]

The package provides an interface to the [Linear Algebra PACKage][1].

## [Documentation][docs]

## Example

```rust
let n = 3;

let mut a = vec![3.0, 1.0, 1.0, 1.0, 3.0, 1.0, 1.0, 1.0, 3.0];
let mut w = vec![0.0; n];
let mut work = vec![0.0; 4 * n];
let lwork = 4 * n as isize;
let mut info = 0;

lapack::dsyev(b'V', b'U', n, &mut a, n, &mut w, &mut work, lwork, &mut info);

for (one, another) in w.iter().zip(&[2.0, 2.0, 5.0]) {
    assert!((one - another).abs() < 1e-14);
}
```

## Contributing

1. Fork the project.
2. Implement your idea.
3. Open a pull request.

[1]: http://en.wikipedia.org/wiki/LAPACK

[version-img]: https://img.shields.io/crates/v/lapack.svg
[version-url]: https://crates.io/crates/lapack
[status-img]: https://travis-ci.org/stainless-steel/lapack.svg?branch=master
[status-url]: https://travis-ci.org/stainless-steel/lapack
[docs]: https://stainless-steel.github.io/lapack
