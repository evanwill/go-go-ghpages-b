---
title: Introduction to Static Web and Jekyll
nav: Jekyll
topics: static web; static generators; Jekyll
description: > 
    Learn about static web approaches, static site generators, and how Jekyll fits in with GitHub Pages. (See video in Blog section)
---

## Static Web

Unlike [WordPress](https://wordpress.com/){:target="_blank" rel="noopener"} or [Drupal](https://www.drupal.org/){:target="_blank" rel="noopener"}, GitHub Pages is not a content management system or dynamic web application.
There is no database, server side processing, or admin interface.

This is known as a [<span class="term">Static Web</span>](https://en.wikipedia.org/wiki/Static_web_page){:target="_blank" rel="noopener"} host. 
HTML, CSS, and JS stored in the repository are served to the user without dynamic changes.
You can think of a static site as a shared folder of readonly files exposed on the web.

In the *olden days* static web was the norm, but database driven dynamic web sites have dominated the last decade.
For example, think of social media sites, where dynamic web applications and huge databases enable features such as user authentication, live comments, and personalized streams. 
All this complex functionality requires heavy server-side infrastructure and processing--which may not be necessary or desireable for all web sites.

Thus, despite their limitations static sites are experiencing a [recent boom](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/){:target="_blank" rel="noopener"} as a viable alternative because they offer some advantages over that heavy infrastructure:

- faster performance (easy caching / CDN, low bandwidth, no processing time).
- minimal hosting requirements (basic web servers, no dependencies, simple development environment).
- minimal security vulnerabilities (no software or server programming language to get hacked).
- easy version control (everything is plain text).

## Static Site Generators

<span class="term">Static Site Generators</span> are software tools that bundle together a stack of web development packages used to transform a directory of source code into a complete website.
With growing interest in static web approaches, such as [Jamstack](https://jamstack.org/){:target="_blank" rel="noopener"}, hundreds of Static Site Generators have sprung onto the scene--browse lists at [Jamstack Site Generators](https://jamstack.org/generators/){:target="_blank" rel="noopener"} and [Static Site Generators](https://staticsitegenerators.net/){:target="_blank" rel="noopener"}.

These tools typically feature: 

- a command line interface (not GUI software).
- a builtin development server (test your site on your computer). 
- simplified markup based content (e.g. write in Markdown).
- web templating language (build a site from modular components pulled together with basic logic).
- CSS preprocessor (e.g. Sass).
- file-based data options (create content from CSVs or JSON).
- plugin extensibility (add new functionality).

----------

## Jekyll 

[Jekyll](https://jekyllrb.com/){:target="_blank" rel="noopener"} is one of the most popular and actively developed static site generators, in part because of its direct integration with GitHub Pages.
Originally focused on creating simple blogs from Markdown files, it has developed into a fully featured generator used on all types of web projects from tiny to huge (browse the [Showcase](https://jekyllrb.com/showcase/){:target="_blank" rel="noopener"}).

{% include figure.html img="jekyll.png" alt="jekyll logo" width="45%" %}

Jekyll is written in the programming language [Ruby](https://www.ruby-lang.org/){:target="_blank" rel="noopener"} and can be installed on your computer as a Ruby Gem--however, *you don't need to know anything about Ruby to get started using it!*

In fact, in the next section of the workshop we will build a Jekyll-powered blog without installing anything and editing entirely in the GitHub web interface.
Once you set up the repository, GitHub Pages' integrated Jekyll service will automatically build out the site after each new commit.

## Jekyll Projects

A basic Jekyll project is a folder of files that looks something like this:

{% include figure.html img="basic-theme.png" alt="Jekyll folder structure including _data, _includes, _layouts, _posts, _sass, _config.yml, and index.md." %}

Content is written in Markdown in files such as `index.md` or items in the `_posts` folder.
The `_includes`, `_layouts`, and `_sass` directories can contain modular components that will flesh out the template of each web page, i.e. the website's theme.
Jekyll knits the content and theme together to build out your website.

However, **you don't need to start from scratch**.
Instead you can use an existing theme to jump start your Jekyll project.

A [Jekyll theme](https://jekyllrb.com/docs/themes/) is basically a packaged set of templates and styles (usually including folders `assets`, `_includes`, `_layouts`, and `_sass`) that can be referenced in your configuration or included directly as part of your project folder.

{% include alert.html color="warning" text="Note: folder and file names starting with an underscore (`_`) are special to Jekyll. Be sure to name them correctly!" %}

-------------

{% capture reference %}
- [GitHub Pages docs](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages)
- [Using Jekyll on GitHub Pages docs](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll)
- [Jekyll docs](https://jekyllrb.com/docs/)
- Find [Jekyll themes on GitHub](https://github.com/topics/jekyll-theme)
- [Jamstack](https://jamstack.org/) and [JAMstack WTF](https://jamstack.wtf/)

{% endcapture %}
{% include card.html text=reference header="Reference" %}
