*This repository is a mirror of the [component](http://component.io) module [gorillatron/funcmatch](http://github.com/gorillatron/funcmatch). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/gorillatron-funcmatch`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# funcmatch

Pattern matching. Create typed functions.

## Installation

```
$ component install gorillatron/funcmatch
```

## Usage

```javascript

var match = require( 'funcmatch' )

var concat = match([String, String], function( a, b ){
                     return a + b
                   },
                   [String, Number], function( a, b ) {
                     return a + '::' + b
                   })

concat( 'foo', 'bar' )
// -> 'foobar'

concat( 'foo', 13 )
// -> 'foo::13

```

### wildcard

```javascript
var __ = match.__

var foo = match([String, __], 'string *',
                [__, Number], '* number')

foo('bar', {})
// -> 'string *'

foo(false, 42)
// -> '* number'

```

## License 

MIT licensed
