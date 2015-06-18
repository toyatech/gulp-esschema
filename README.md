gulp-esschema
============

## Usage:

```javascript
var gulp    = require('gulp'),
    esprima = require('gulp-esprima'),
    esschema = require('gulp-esschema');

// This task will use esprima to parse all of the JavaScript files 
// under schema/, generate and save JSON Schema representations of 
// their ASTs (abstract syntax trees) under dist/schemas/
gulp.task('generate', function() {
  return gulp.src('schemas/*.js')
    .pipe(esprima()) // or esprima({ [options] })
    .pipe(esschema()) // or esschema({ [options] })
    .pipe(gulp.dest('dist/schemas/'));
});
```

This plugin accepts two options:

- `pretty`: for nicely indented JSON (default: `false`)
- `esschema`: options to pass directly to `esschema.generate`
