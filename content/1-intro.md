---
title: Introduction to GitHub
nav: Intro
topics: github; gh-pages; README; Markdown; HTML
description: >
    This section introduces the GitHub web interface, walks through creating a repository, and covers the basics of Markdown and HTML. 
    These topics are important for understanding the basic building blocks of websites and learning how to work with files on GitHub.
youtubeid: SWVjQsvQocA
---

## Git -> GitHub -> GitHub Pages

Before we get started we better clarify some terms:

[<span class="h4">Git</span>](https://git-scm.com/){:target="_blank" rel="noopener"} is a popular [free](https://www.gnu.org/philosophy/free-sw.en.html){:target="_blank" rel="noopener"}, [distributed version control](https://en.wikipedia.org/wiki/Distributed_version_control){:target="_blank" rel="noopener"} system--i.e. a piece of software used to track the history of changes in a folder of files. 
Git can be used on your personal computer, or by online services to track the development of a project, such as...

[<span class="h4">GitHub</span>](https://github.com/){:target="_blank" rel="noopener"}, a popular web platform for hosting Git repositories--i.e. a place to store and sync your project files online.
Built around the powerful version control of Git, it provides a handy web interface for managing, editing, and collaborating on repositories.

Originally designed to manage large open-source software projects, GitHub's use has expanded to many other types of organizations and individuals, with [over 40 million users](https://octoverse.github.com/).
GitHub provides a bunch of built in project management features including...

{% include figure.html img="octojekyll.png" alt="Octojekyll logo" width="35%" %}

[<span class="h4">GitHub Pages</span>](https://pages.github.com/){:target="_blank" rel="noopener"}, free static web hosting service available as part of every repository--this means with the *click of a button* you can fire up a new website!

Intended to host relatively simple sites for your GitHub portfolio or project documentation,
GitHub Pages is an ideal solution for creating an open educational resource or personal site to highlight your academic work. 
Because hosting through gh-pages is free and builds valuable transferable skills, this is a great option for teaching and learning.
Users have the opportunity to become creators and participants in global digital culture, developing critical digital literacy about the fabric of the web.

Many organizations and individuals are using GitHub to collaboratively create and publish public websites. 
For example:

- [Programming Historian](http://programminghistorian.org/){:target="_blank" rel="noopener"}
- [The Carpentries](https://carpentries.org/){:target="_blank" rel="noopener"}
- this site!

{% capture text %}
There are *soft* limits and guidelines for gh-pages usage: sites should be < 1GB, use < 100GB bandwidth per month, and make < 10 builds per hour.
If your site exceeds these quotas, GitHub will send you a notice asking you to modify the repository.

All content must follow the [community guidelines](https://help.github.com/articles/github-community-guidelines/), e.g. no violence, obscene sex, or illegal stuff.{% endcapture %}
{% include alert.html text=text color=secondary %}

----------------

## GitHub Practice

Let's create a new repository, then write some Markdown and HTML to see how gh-pages works!

### Create a New Repository 

- create a repo, 
    - intro to github
    - intro to repo features
    - intro to activate gh-pages

### Edit your README (Markdown Intro)

- edit README.md 
    - intro to readme conventions
    - intro to web editor
    - intro to markdown, headers, paragraphs, links, inline elements
    - intro to first commit 
    - view rendered


[Markdown](https://daringfireball.net/projects/markdown/) is a standard to [simplify writing](https://evanwill.github.io/_drafts/notes/writing-markdown.html) content for the web. 
[GitHub markdown flavor](https://help.github.com/articles/basic-writing-and-formatting-syntax/) can be used any where on GitHub and in Jekyll.
The basics are intuitive, you can learn in about a minute!
See [Markdown in a Minute](https://evanwill.github.io/_drafts/notes/markdown-minute.html) to get started.


### Create index.html (HTML Intro)

- create a file, index.html 
    - intro to index.html convention
    - intro to html (relation to markdown)
    - intro to second commit
    - intro to urls (to find the page)
    - wait for build, view site

-------------

## Reference 

**Git & GitHub:**

- [GitHub Guides](https://guides.github.com/){:target="_blank" rel="noopener"}, see [Hello World](https://guides.github.com/activities/hello-world/){:target="_blank" rel="noopener"} for an introduction.
- [GitHub Learning Lab](https://lab.github.com/){:target="_blank" rel="noopener"}

**Markdown:**

- [Markdown](https://daringfireball.net/projects/markdown/) 
- [Markdown in a Minute](https://evanwill.github.io/_drafts/notes/markdown-minute.html)
- GitHub Guide [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
- [GitHub markdown flavor](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
