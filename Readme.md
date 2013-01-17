![Build Status](https://travis-ci.org/bengourley/node-directory-copy.png?branch=master)

## Install:

```
npm install directory-copy
```

## Usage:

```js
var copy = require('directory-copy')
```

### copy(options, cb)

- `options` is an options hash
  - `src` the source directory (required)
  - `dest` the destination directory (required)
  - `excludes` an array of RegExp objects to `.test()` filenames
    against. If the test returns true, the file won't be copied.
  - `logger` a custom logger object, defaults to console.log
- `cb` is the callback `function (err) {}` (`err` is null if ok)

Eg:
```js
copy(
    { src: __dirname + '/source/static'
    , dest: __dirname + '/output/static'
    , excludes: /^\./ // Exclude hidden files
    }
  , function () {
    console.log('done!')
  })
```