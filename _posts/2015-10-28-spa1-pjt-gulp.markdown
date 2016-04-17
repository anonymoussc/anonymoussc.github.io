---
title:  "SPA1 Pjt - Gulp"
date:   2015-10-24 08:05:00
summary: gulp & gulp watcher.
---

A build tool based on NodeJS

### Feature used (Gulp watcher on)

Type `gulp watch` in root directory, it will watch directory, file and automaticaly do :

- Bower : concatenated, minified js (all into vendor.js), css (all into vendor.css) whenever new bower package install detected.
- AngularJS : annotated, concatenated, minified angularJS file (all into app.js) whenever any js file saved, automaticaly.
- Preprocessor less : preprocess, concatenated, minified  .less (all into app.css) whenever any .less file saved, automaticaly.
- Preprocessor sass : preprocess, concatenated, minified  .scss (all into app.css) whenever any .scss file saved, automaticaly.
- jshint : detect error, bug, typo etc in js file (also line) and offer suggestion.
- jscs : detect error, bug, typo etc in js file (also line) and offer suggestion, autofix jscs problem.
- copy view template - deprecated.
- Transform html file into javascript : since single page application will download all javascript file first, it will give superior performance boost. Html / view template never need to be asynchronously requested. Its works automatically whenever any js file saved.
- auto reload - Automatically reload browser whenever detect any file changed, example in app.js, vendor.css etc.