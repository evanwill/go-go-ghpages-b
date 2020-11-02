---
title: Customizing with Layouts and Liquid
nav: Advanced
topics: layouts; Liquid; Liquid variables; includes; data
description: >
    This section introduces customizing your Jekyll theme and pages by adding new layouts, includes, and data.
---

## Create a New Layout (_layouts)

- create _layouts/dark.html 
    - intro to layouts
    - cascading layouts

## Using Liquid Variables

- create about.md 
    - use new layout
- edit about.md
    - intro to Liquid variables in page
    - commit 

## Using Liquid Includes (_includes)

- create _includes/bigcat.html
    - intro to includes
    - use to add image to index.md

## Using Data (_data) and Advanced Liquid

- create _data/animals.csv
    - intro to data folder 
    - create csv
    - intro to Liquid data and for loop 
    - use to add list to about.md
    - add an Liquid if


-------------

{% capture reference %}


{% endcapture %}
{% include card.html text=reference header="Reference" %}


### Liquid

[Liquid](http://shopify.github.io/liquid/) is a flexible template language.
[In Jekyll](https://jekyllrb.com/docs/templates/) it allows you to layout pages built from modular components and data, using the `_includes`, `_layouts`, and `_data` directories.
Liquid includes features such as operators, loops, and filters to manipulate raw content. 
Liquid statements are enclosed by {% raw %}`{%  %}`{% endraw %} and variables in {% raw %}`{{  }}`{% endraw %}.
