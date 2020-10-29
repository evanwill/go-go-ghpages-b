---
title: Customizing with Layouts and Liquid
nav: Advanced
topics: layouts; Liquid; Liquid variables; includes; data
---

advanced
- create _layout/dark.html 
    - intro to layouts
    - cascading layouts
- create about.md 
    - use new layout
- edit about.md
    - intro to Liquid variables in page
    - commit 
- create _include/bigcat.html
    - intro to includes
    - use to add image to index.md
- create _data/animals.csv
    - intro to data folder 
    - create csv
    - intro to Liquid data and for loop 
    - use to add list to about.md
    - add an Liquid if


### Liquid

[Liquid](http://shopify.github.io/liquid/) is a flexible template language.
[In Jekyll](https://jekyllrb.com/docs/templates/) it allows you to layout pages built from modular components and data, using the `_includes`, `_layouts`, and `_data` directories.
Liquid includes features such as operators, loops, and filters to manipulate raw content. 
Liquid statements are enclosed by {% raw %}`{%  %}`{% endraw %} and variables in {% raw %}`{{  }}`{% endraw %}.
