---
title: Developing with Jekyll
nav: Dev
topics: text editor; git; ruby; Jekyll 
description: > 
    Want to go further? The next steps involve getting set up to develop Jekyll sites on your own computer. This section walks through the necessary software and introduces the basic workflow.
youtubeid: QW7BXZ78RgM
---

## Development Environment 

To work with Jekyll on your local machine you will need some software installed on your computer, including: 

- A text editor
- Git
- Ruby (2.5 +)
- Jekyll 

Getting everything set up can be a major hurdle, but stick with it!
This environment will empower you to edit code, version control, manage your files, and create websites--so its pretty neat and rewarding.

### Text Editor

When working with code you need a good text editor.

Word processors such as MS Word can not be used to create or edit code.
Windows Notepad does not handle UTF-8 encoding or UNIX line endings that are standard for cross platform applications. 

For basic editing, Windows [Notepad++](https://notepad-plus-plus.org/), Mac TextEdit, or Linux Gedit are sufficient.
However, a more complete code editor will be helpful for managing Jekyll projects.
Try one of these open source, cross platform options:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Atom](https://atom.io/)

These editors will allow you to work on whole folders of files at once (i.e. your Jekyll project repository) and have built in helpers for using and visualization Git. 

### Git

[Git](https://git-scm.com/) is a [free](https://www.gnu.org/philosophy/free-sw.en.html), [distributed version control](https://en.wikipedia.org/wiki/Distributed_version_control) system. 
[GitHub](https://github.com/) is a Git repository hosting service, a place to store and sync your work in the cloud.
Your GitHub Pages projects will be under Git version control, so you need the software on your machine to work with it locally.

Installing it is pretty straightforward:

- Windows: install [Git for Windows](https://git-for-windows.github.io/) using the default options, except when setup asks you to choose the default editor used by Git, select "Use the Nano editor by default". This will give you Git, Git Bash, and Git GUI. Git Bash is a great terminal that lets you use UNIX style commands and utilities on Windows.
- Mac: you will need "Xcode Command Line Tools" installed, so open a terminal (to find it search for "terminal" in Spotlight), type in the command `xcode-select --install`, and follow the prompts. After the install finishes, try typing `git --version`. If you want a newer version, download the official [Mac installer](https://git-scm.com/downloads).
- Linux: check if Git is already installed by opening terminal and typing `git --version`. If you do not have it, install from your distribution's package manager (for Ubuntu `sudo apt install git`).

If you are interested in using a visual GUI application integrated with GitHub, Windows and Mac users should also install [GitHub Desktop](https://desktop.github.com/) using the default options.
You can install GitHub Desktop in addition to other versions of Git.
There are other [GUI apps available](https://git-scm.com/downloads/guis) for managing and visualizing Git repositories, including Linux options.

Generally, it is easiest to start your project repository on GitHub, then `clone` the repository to your local machine to start working on it. 
This ensures your local copy is linked to the `remote` on GitHub. 

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

[Jekyll](https://jekyllrb.com/) is a Gem, a software package installed via Ruby's management system called RubyGems (similar to Python's Pip). 

To install Jekyll, open a terminal and type:

`gem install jekyll bundler`

This will take a minute or two as Gem installs all the dependencies and builds extensions (on Windows it may appear as if nothing is happening, but be patient!).
Jekyll is made up of dozens of other Ruby Gems, so [Bundler](https://bundler.io/) is a helper to manage dependencies. 
If you are just using Ruby for Jekyll on smaller projects, you hopefully won't have to deal with Bundler and the maze of dependencies!
For more details see Jekyll's [Installation guides](https://jekyllrb.com/docs/installation/).

-------------------------

## Start a Jekyll Project 

As a demonstration, let's create a basic Bootstrap website using an existing template. 
In this case we are not using Jekyll `theme`, instead all the "theme" files will be contained inside the repository.
This makes it easier to customize than working with the Gem based theme system.

Overview:

1. Go to the [bootstrap-template repository](https://github.com/thecdil/bootstrap-template) on GitHub.
2. Make your own copy of the code on GitHub by clicking the green "Use this template" button (alternatively use Import, or just download the code and copy the files into your own repo).
3. Clone your new repository to your local machine (using Git or GitHub Desktop, click the green "Code" button for the link).
4. Open the repository folder in your text editor.
5. Edit the `_config.yml` with your project info (i.e. edit `title`, `description`, `year`, and `author` for your project). Then Git Commit!
6. In the root of your repository, start a Terminal (or use one built into your text editor). Type the command `jekyll s` to start the development server. Copy the localhost URL it provides, paste into a private browser tab to view your site locally.
7. In the "pages" folder, edit the stubs in Markdown to create content (see [bootstrap-template docs](https://github.com/thecdil/bootstrap-template/blob/main/docs/create-website.md){:target="_blank" rel="noopener"} for options). And Git Commit!
8. Customize with Sass/CSS, edit "assets/css/custom.scss", "_sass/_custom.scss", "_data/theme-colors.csv" (options built into bootstrap-template). And Git Commit!
9. When done, Git Commit all changes, and Git Push to GitHub.
10. Activate GitHub Pages in your repository's Settings.
11. Enjoy website!

-------------

{% capture reference %}
- [Jekyll step-by-step introduction](https://jekyllrb.com/docs/step-by-step/01-setup/){:target="_blank" rel="noopener"}
- [bootstrap-template docs](https://github.com/thecdil/bootstrap-template/blob/main/docs/create-website.md){:target="_blank" rel="noopener"}
- [Bootstrap](https://getbootstrap.com/) (front-end framework)

{% endcapture %}
{% include card.html text=reference header="Reference" %}
