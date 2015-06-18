gulp-esschema
============

## Usage:

```javascript
var gulp    = require('gulp'),
    esprima = require('gulp-esprima'),
    esschema = require('gulp-esschema');

// This task will parse all of the JavaScript files under lib/
// and save JSON representations of their ASTs (abstract syntax
// trees) under parsed/
gulp.task('generate', function() {
  return gulp.src('schemas/*.ess')
    .pipe(esprima())
    .pipe(esschema())
    .pipe(gulp.dest('dist/schemas/'));
});
```

This plugin accepts two options:

- `pretty`: for nicely indented JSON (default: `false`)
- `esschema`: options to pass directly to `esschema.generate`
