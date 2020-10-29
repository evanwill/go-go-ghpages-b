---
title: Introduction to Jekyll and Static Web
nav: Jekyll
topics: Jekyll; static web; static generators
description: > 
    Learn about static web approaches, static site generators, and how Jekyll fits in with GitHub Pages.
---

# Jekyll 

- intro to Jekyll 
    - background
        - static web
        - static generators
        - ruby
        - gh-pages
    - components of jekyll project
        - a folder of files
        - we are going to use a theme, so we don't seem most of the project


## Static Web

Unlike [WordPress](https://wordpress.com/){:target="_blank" rel="noopener"} or [Drupal](https://www.drupal.org/){:target="_blank" rel="noopener"}, gh-pages is not a content management system or dynamic web application.
There is no database, server side language / processing, or admin interface.
This is known as a [static web](https://en.wikipedia.org/wiki/Static_web_page){:target="_blank" rel="noopener"} host. 
HTML, CSS, and JS stored in the repository are served to the user without dynamic changes.

In the olden days static web was the norm, but database driven dynamic web sites have dominated the last decade.
Dynamic web applications enable features such as live comments, user authentication, and personalized streams. 
However, this functionality requires complex server-side infrastructure and processing.

> `view-source:` one fascinating aspect of the web is that everyone must share code to participate. 
> Right click on any web page and select "View page source" to see the code that is being rendered by the browser.
> Right click on any element in the page and select "Inspect" or "Inspect Element" to open your browser's built in developer tools.
> This is a great way to learn about HTML and to understand how others created the sites you use.

Despite their limitations static sites are experiencing a [new boom](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/){:target="_blank" rel="noopener"}, because they offer some significant advantages:
- much faster performance (caching, low bandwidth, no processing time).
- low hosting requirements (simple web servers, no dependencies).
- no security vulnerabilities.
- easy version control.

To make development easier, hundreds of static site generators have sprung onto the scene (see lists at [StaticGen](https://www.staticgen.com/){:target="_blank" rel="noopener"} and [Static Site Generators](https://staticsitegenerators.net/){:target="_blank" rel="noopener"}).
Static generators bundle together a stack of web development tools which are used to transform a directory of source code into a deployable web site.

[Jekyll](https://jekyllrb.com/){:target="_blank" rel="noopener"} is one of the most popular and actively developed, in part because of its integration with gh-pages.
*More on that later...*

> Static Site Generators typically feature: command line interface; builtin development server; simplified markup based content; web templating language; CSS preprocessor; file-based data options; plugin extensibility. 

