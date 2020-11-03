---
title: Developing with Jekyll
nav: Dev
topics: text editor; git; ruby; Jekyll 
description: > 
    Want to go further? The next steps involve getting set up to develop Jekyll sites on your own computer. This section walks through the necessary software and introduces the basic workflow.
---

If you are excited to jump further into GitHub Pages and Jekyll you might want some additional software installed on your computer, 
including a text editor, Git, Ruby, and Jekyll.
The instructions below will set up your local development environment and provide a bit of background.

### Text Editor

When working with code you should have a good text editor.
Word processors such as MS Word can not be used to create or edit code.
Windows Notepad does not handle UTF-8 encoding or UNIX line endings that are standard for cross platform applications. 

For basic editing, Windows [Notepad++](https://notepad-plus-plus.org/), Mac TextEdit, or Linux Gedit are sufficient.
However, a more complete code editor will be helpful for managing Jekyll projects.

Open-source cross platform suggestions:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Atom](https://atom.io/)

### Git

[Git](https://git-scm.com/) is a [free](https://www.gnu.org/philosophy/free-sw.en.html), [distributed version control](https://en.wikipedia.org/wiki/Distributed_version_control) system. 
[GitHub](https://github.com/) is a Git repository hosting service, a place to store and sync your work in the cloud.
Your GitHub Pages projects will be under Git version control, so you need the software on your machine to work with it locally.

Installing it is pretty straightforward:

- Windows: install [Git for Windows](https://git-for-windows.github.io/) using the default options, except when setup asks you to choose the default editor used by Git, select "Use the Nano editor by default". This will give you Git, Git Bash, and Git GUI. Git Bash is a great terminal that lets you use UNIX style commands and utilities on Windows.
- Mac: check if Git is already installed by opening terminal and typing `git --version`. If you do not have it, download the official [Mac installer](https://git-scm.com/downloads).
- Linux: check if Git is already installed by opening terminal and typing `git --version`. If you do not have it, install from your distribution's software center or package manager (for Ubuntu `sudo apt install git`).

If you are interested in using a visual GUI application integrated with GitHub, Windows and Mac users should also install [GitHub Desktop](https://desktop.github.com/) using the default options.
You can install GitHub Desktop in addition to other versions of Git.

There are other [GUI apps available](https://git-scm.com/downloads/guis) for managing and visualizing Git repositories, including Linux options.

### Ruby

[Ruby](https://www.ruby-lang.org/){:target="_blank" rel="noopener"} is a programming language popular with web applications.
*You do not need to know anything about Ruby*, but you do need it to run Jekyll on your system!
If you are curious to learn, check out [Ruby in 20 minutes](https://www.ruby-lang.org/en/documentation/quickstart/) or [Try Ruby in your browser](https://try.ruby-lang.org/).

Jekyll requires a Ruby version 2.5.0 or higher installed on your computer.
Installing Ruby isn't super easy, but [Jekyll install docs](https://jekyllrb.com/docs/installation/) have detailed guides for getting set up on different operating systems.
Here is a short summary:

{% capture ruby %}
- **Windows:** [RubyInstaller for Windows](https://rubyinstaller.org/) makes install pretty easy. 
    - First, [download](https://rubyinstaller.org/downloads/) the suggested stable version "WITH DEVKIT" (as of this writing, Ruby+Devkit 2.7.X (x64)) and double click to install. Use the install defaults, but make sure "Add Ruby executables to your PATH" is checked. On the final step, ensure the box to start the MSYS2 DevKit is checked.
    - Second, the installer will open a terminal window with options to install MSYS2 DevKit components. Choose option 3, "MSYS2 and MINGW development toolchain", or simply press ENTER to install all the necessary dependencies. (This installer can be restarted by typing `ridk install` into a command prompt)
- **Mac:** OS X has a version of Ruby installed by default. Check the version with `ruby -v`. If it is > 2.5.0 you can use the system Ruby. However, it is usually preferable to install a newer version using a manager such as [rbenv](https://github.com/rbenv/rbenv) or [RVM](http://rvm.io/). Installing Ruby on Mac is often confusing, so check the official Jekyll [Mac install docs](https://jekyllrb.com/docs/installation/#macOS) for tips.
- **Linux:** Even though the version will not be the most up-to-date, the simplest method is to use your distro's repositories. For example on Ubuntu, `sudo apt install ruby-full`. Make sure the repository version is > 2.5.0. You will also need the build tools Make and GCC, on Ubuntu get them with `sudo apt install build-essential`. However, it is usually preferable to use a manager such as [rbenv](https://github.com/rbenv/rbenv) or [RVM](http://rvm.io/).
{% endcapture %}
{% include card.html text=ruby header="Install Ruby" %}

### Jekyll

Jekyll is a Gem, a software package installed via Ruby's management system called RubyGems (similar to Python's Pip). 

To install Jekyll, open a terminal and type:
`gem install jekyll bundler`

This will take a minute or two as Gem installs all the dependencies and builds extensions (on Windows it may appear as if nothing is happening, but be patient!).


### Sass  

[Sass](http://sass-lang.com/) is a CSS extension / preprocessor. 
All normal CSS is valid SCSS, but Sass adds many powerful functions and programatic features. 
Writing SCSS is often easier and more sensible, for example by supporting nesting, variables, and operators. 
Jekyll lets you write SASS in modular chucks called partials, in the `_sass` directory, that will be combined and compiled into normal CSS files when the site is built.

