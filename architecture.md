#Introduction

I wanted to add a new set of directive to dashboard dealing with a paging controller. I selected angular-paging directive [see](https://www.npmjs.com/package/angular-paging). 

The result is that ![alt tag](https://raw.githubusercontent.com/brantwills/Angular-Paging/gh-pages/basicSample.png)

Or that ![alt tag](https://raw.githubusercontent.com/brantwills/Angular-Paging/gh-pages/advancedSample.png)

And the directive can be as simple as that

```html
<div paging
  page="35" 
  page-size="10" 
  total="1000"
  paging-action="foo('bar', page)">
</div>
```

This widget is very pleasent to browse big data spaces like we enconter browsing database for example. You can see this [gist](https://github.com/gbrault/gistfiles/blob/master/knex/sql.md)

#File changes

* README.md: warn that there are some changes compared to main stream
* architecture.md: describe what the changes are about
* package.json: name of the package, +	"angular-paging": "^2.2.2", +	"bootstrap":"^3.3.7"
* src/index.html: added the exact links to angular-paging and bootstrap js and css resources
* src/main.js: adding 'bw.paging' angular directive to 'ui' application

#What do we need to change?

* The 'ui' application list of module => main.js adding the 'bw.paging' directive
```javascript
var app = angular.module('ui', ['ngMaterial', 'ngMdIcons', 'ngSanitize', 'sprintf', 'chart.js', 'bw.paging']);
```
As you can see, by default, node-red dashboard use 'ngMaterial', 'ngMdIcons', 'ngSanitize', 'sprintf' directives and 'chart.js' is new with this release (2.2.0-beta)
For more information about the bw.paging directive, please, [see](https://github.com/brantwills/Angular-Paging)

* Add resources needed by bw.paging: adding them to package.json: in the development section I have added two npm package

```json
"angular-paging": "^2.2.2",
"bootstrap":"^3.3.7"
```
angular paging is doing the paging script
bootstrap is providing the widget (js and css) side

* We need then to add the resources in the index.html file

 * bootstrap css
```html
<link rel="stylesheet" href="vendor/bootstrap/dist/css/bootstrap.min.css">
     <!-- endbuild -->  <== This was existant
```
 * bw.paging angular directives and boostrap javascript

```html
<!-- for paging -->
<script src="vendor/angular-paging/dist/paging.min.js"></script>
<script src="vendor/bootstrap/dist/js/bootstrap.min.js"></script>
```

# Building

* in node-red-dashboard directory
  * ```npm install``` to get all the necessary resources uploaded (node_modules directory)
  * ```gulp``` to 'compile' all the resources into the dist directory
  
And beleive it or not: it works with no apparent side-effect: magic!
