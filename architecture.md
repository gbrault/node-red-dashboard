#Introduction

I wanted to add a new set of directive to dashboard dealing with a paging controller. I selected angular-paging directive [see](https://www.npmjs.com/package/angular-paging). 

The result is that ![alt tag](https://raw.githubusercontent.com/brantwills/Angular-Paging/gh-pages/basicSample.png)

#File changes

* README.md: warn that there are some changes compared to main stream
* architecture.md: describe what the changes are about
* package.json: name of the package, +	"angular-paging": "^2.2.2", +	"bootstrap":"^3.3.7"
* src/index.html: added the exact links to angula-paging and bootstrap js and css resources
* src/main.js: adding 'bw.paging' angular directive to 'ui' application
