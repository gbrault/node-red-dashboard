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

This widget is very pleasent to browse big data spaces like we enconter browsing database for example

#File changes

* README.md: warn that there are some changes compared to main stream
* architecture.md: describe what the changes are about
* package.json: name of the package, +	"angular-paging": "^2.2.2", +	"bootstrap":"^3.3.7"
* src/index.html: added the exact links to angula-paging and bootstrap js and css resources
* src/main.js: adding 'bw.paging' angular directive to 'ui' application

#What do we need to change?

* The 'ui' application list of module => main.js adding the 'bw.paging' directive
```javascript
var app = angular.module('ui', ['ngMaterial', 'ngMdIcons', 'ngSanitize', 'sprintf', 'chart.js', 'bw.paging']);
```