gulp-zopfli-node
===========

a [Zopfli](http://en.wikipedia.org/wiki/Zopfli) plugin for [gulp](https://github.com/wearefractal/gulp),
based on [`zopfli-node`][zopfli-node].

**Note:** This is a fork of [gulp-zopfli](https://npmjs.org/package/gulp-zopfli) that hasn't been updated in a long time and uses an old version of [`node-zopfli`][node-zopfli] (replaced by [`zopfli-node`][zopfli-node] in this package).

[![NPM version][npm-image]][npm-url]
[![Dependency Status][dep-image]][dep-url]
[![devDependency Status][devDep-image]][devDep-url]

## Install

```
npm install --save-dev gulp-zopfli
```

##Options

### format `String`

Choose an output format, you can choose between `gzip`, `zlib` or `deflate`. Defaults to gzip.

```javascript
 zopfli({ format: 'zlib' })
 ```


### append `Boolean`

Appends `.gz`, `.zz` or `.deflate` file extension if true depending on the format chosen. Defaults to true.

```javascript
 zopfli({ append: true })
 ```

### threshold `String|Number|Boolean`

Minimum size required to compress a file. Defaults to false.

```javascript
zopfli({ threshold: '1kb' })
```

```javascript
zopfli({ threshold: 1024 })
```

```javascript
zopfli({ threshold: true })
```

### zopfliOptions `Object`

Options object to pass through to zopfli-node. See [zopfli-node documentation](https://github.com/molant/node-zopfli#options) for more information.

```javascript
{
    verbose: false,
    verbose_more: false,
    numiterations: 15,
    blocksplitting: true,
    blocksplittinglast: false,
    blocksplittingmax: 15
};
```

## Examples

```javascript
var gulp = require("gulp");
var zopfli = require("gulp-zopfli");

gulp.task("compress", function() {
	gulp.src("./dev/scripts/*.js")
	.pipe(zopfli())
	.pipe(gulp.dest("./public/scripts"));
});

gulp.task("default", function() {
  gulp.run("compress");
});
```

Credit
======

This plugin is based on [gulp-gzip](https://github.com/jstuckey/gulp-gzip).


[npm-image]: https://img.shields.io/npm/v/gulp-zopfli-node.svg
[npm-url]: https://www.npmjs.com/package/gulp-zopfli-node
[dep-image]: https://img.shields.io/david/molant/gulp-zopfli.svg
[dep-url]: https://david-dm.org/molant/gulp-zopfli
[devDep-image]: https://img.shields.io/david/dev/molant/gulp-zopfli.svg
[devDep-url]: https://david-dm.org/molant/gulp-zopfli#info=devDependencies
[node-zopfli]: https://npmjs.org/package/node-zopfli
[zopfli-node]: https://npmjs.org/package/zopfli-node
