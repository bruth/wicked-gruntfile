## Wicked Gruntfile

Gruntfile which manages source files from local development, intermediate compilation, and distribution builds.

### Install

Fill out `package.json` with metadata. Install development dependencies:

```bash
npm install
```

### Tasks

- `grunt local` - Populates the `local/` directory with compiled CoffeeScript and SCSS files and copies over other non-compiled source files
- `grunt work` - Runs the `local` tasks and ends with a watcher that compiles to `local/` on the fly
- `grunt dist` - Populates the `dist/` directory for a distribution build
- `grunt test` - Runs the Jasmine specs in `spec/` against a fresh local build
- `grunt release` - Creates a zip and gzip tarball of the distribution files in a directory named after the package
- `grunt serve:forever` - Launches a node server on port 8125 by default. Useful for viewing Jasmine tests in the browser

### Directory Structure

```bash
package.json
Gruntfile.coffee
# location of Jasmine spec files
spec/
    ...
# source files for all types
src/
    coffee/
    js/
    scss/
    css/
    img/
    fonts/
    templates/
# created by Grunt for local development
local/
    ...
# intermediate build directory for CoffeeScript files,
# before minification using r.js
build/
    ...
# final resting place of built files in their respective
# directories
dist/
    ...
```
