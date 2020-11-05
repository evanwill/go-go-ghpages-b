---
title: Layouts, Includes, Data, & Liquid
nav: Theme
topics: layouts; includes; data; Liquid; Liquid variables
description: >
    In this section of the workshop we will create a Layout, Include, and Data file--then we will use Liquid to pull it all together.
    This will give you a better idea of how the components of a Jekyll project fit together to customize a theme or build your own.
youtubeid: BdhLjm4VUKc
---

## Customizing Themes

In the last section we set up a basic Jekyll blog using the Minima theme.
There are several methods to start personalizing the look and feel.

**Theme customization options:** The theme's documentation (often the README) should include information about built in configuration methods. 
For example, Minima has a `skin` option that can change the color palette for the entire site. 
Try adding this option to your `_config.yml`:

```
minima:
  skin: dark
```

**Override existing theme files:** If you place a file in the same location as a file in the theme, the version in your repository will replace it when Jekyll builds your site. 
This option requires good knowledge of how the theme works and examining the file structure to understand where to override.

**Add new theme elements:** You don't have to limit yourself to creating new content, you can also easily add theme elements to extend your project. 
Create new Layouts, Includes, or other files in your project to implement the features you want.

We will look at *basic* examples of the final option in this section by setting up a new Layout, Include, and Data file before using Liquid to pull all these new features into our About page.

{% capture liquid %}
In the Layout and Include examples below you will notice a bit of Liquid code denoted by curly braces like {% raw %}`{{ variable }}`{% endraw %} or {% raw %}`{% function %}`{% endraw %}.
We will cover the details of Liquid after setting up these new components so that we have something interesting to work with!
{% endcapture %}
{% include alert.html text=liquid color="warning" %}

----------------

## Layouts

The basic building blocks of themes are <span class="terms">[Layouts](https://jekyllrb.com/docs/layouts/){:target="_blank" rel="noopener"}</span> which provide the template elements surrounding your content.

Each theme typically starts with a `_layouts/default.html` representing the base HTML that will appear on every page in the generated website (e.g. [Minima's default layout](https://github.com/jekyll/minima/blob/master/_layouts/default.html){:target="_blank" rel="noopener"}).
Other layouts usually have a `layout` in YAML front matter, cascading back to `default` which ensures your template will be consistent without repeating code (e.g. [Minima's page layout](https://github.com/jekyll/minima/blob/master/_layouts/page.html){:target="_blank" rel="noopener"}).

Layouts are written in HTML with some Liquid mixed in. 

We can customize the `_layouts` of our remote_theme by overriding an existing file or adding a new one.

### Create _layouts

Let's create a new (*not very good*) "dark" layout to demonstrate how this works:

- On your repository's home page, click the "Add file" button and select "Create new file". 
- Start by typing `_layouts` followed by `/`. Adding the slash will automatically let GitHub know you want to create a new folder ("_layouts"). 
- Continue typing your new layout filename: `dark.html`
- Add the layout HTML, following the (*rather silly*) example below.
- Fill in your "commit message" and click the green "Commit changes" button.

{% raw %}```
---
layout: page
---
<div style="background:black; color: white; padding: 25px;">
    {{ content }}
</div>
```{% endraw %}

Notice that our new layout has YAML Front Matter including `layout: page`. 
The layouts cascade between each other, being wrapped by the template of their parents.

For example, if we have a new page with front matter `layout: dark`, all the content written on the page will be inserted into the {% raw %}`{{ content }}`{% endraw %} variable seen in the `_layouts/dark.html` above. 
The content + dark layout, will then in turn get wrapped by the template in `_layouts/page.html`. 
Then the content + dark + page layout will get wrapped by the template in `_layouts/default.html` to complete the HTML.

-----------

## Includes 

<span class="term">[Includes](https://jekyllrb.com/docs/includes/){:target="_blank" rel="noopener"}</span> allow you to insert content from another file into your layouts and pages.
This enables you to create modular content chunks that will be reused (e.g. the navbar or header section) or reuseable templates for repeating content types (e.g. a figure image or alert).

For example, we might want to set up a template for a YouTube video embed, as used on this workshop site. 
The file `_includes/video-embed.html` will contain the HTML template using Liquid to fill in the necessary variables.
To add an embed to a page, rather than having to rewrite the embed for each instance, we would use the Liquid code like:

{% raw %}`{% include video-embed.html youtubeid="SWVjQsvQocA" %}`{% endraw %}

### Create _includes

Let's create a new (*not very useful*) "big-cat" include to demonstrate how this works:

- On your repository's home page, click the "Add file" button and select "Create new file". 
- Type your new include filename: `_includes/big-cat.html`
- Add the include HTML, following the (*very silly*) example below.
- Fill in your "commit message" and click the green "Commit changes" button.

```{% raw %}
{% comment %} 
    this include adds a picture of a big cat from Wikimedia, S. Taheri,
    https://commons.wikimedia.org/wiki/File:Siberischer_tiger_de_edit02.jpg 
{% endcomment %}
<img style="display:block; margin: 10px auto;" 
    src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/41/Siberischer_tiger_de_edit02.jpg/640px-Siberischer_tiger_de_edit02.jpg" 
    alt="face of a big tiger" >
{% endraw %}
```

------------

## Data

Jekyll's `_data` directory allows you to add <span class="term">[Data](https://jekyllrb.com/docs/datafiles/){:target="_blank" rel="noopener"}</span> to your site that can be pulled into layouts and pages to create content. 

For example, imagine you have a list of people and you want to add a directory feature to your About page.
Rather than manually writing out and formatting all the people in Markdown, you could maintain the list as a spreadsheet in `_data` and use Liquid to add it to the page.

Any feature made up of repeating content could be a good candidate to move into a data file--e.g. image galleries, FAQs, tables, reference lists, or directories.
Jekyll supports YAML, JSON, CSV, and TSV formats.

For example, you could create a spreadsheet on Google Sheets to collaborate, then download it as a CSV to add to your project in `_data`.

### Create _data

To add some example data to our blog, let's manually create a CSV:

- On your repository's home page, click the "Add file" button and select "Create new file". 
- Type your new data filename: `_data/animal.csv`
- Add the include HTML, following the (*extremely frivolous*) example below.
- Fill in your "commit message" and click the green "Commit changes" button.

```
name,size,color
cat,small,black
dog,medium,brown
frog,small,green
tiger,large,orange
elephant,large,grey
muffin,small,brown
whale,large,blue

```

------------

## Liquid Template Language

At the heart of the build process knitting your website together is the template language <span class="term">[Liquid](https://shopify.github.io/liquid/){:target="_blank" rel="noopener"}</span>.
It allows your pages and layouts to pull in variables and modular components out of your site's complete data.
Liquid includes basic programming features such as operators, loops, and filters to manipulate raw content. 

There are three types of Liquid statements used in Jekyll:

- **objects** pull in values from variables in the project, and are enclosed by double curly braces {% raw %}`{{  }}`{% endraw %}, e.g. {% raw %}`{{ site.title }}`{% endraw %}
- **filters** modify an object, and are added to the object following a pipe `|`, e.g. {% raw %}`{{ site.title | capitalize }}`{% endraw %}
- **tags** add logic, flow control, and iteration to your templates, and are enclosed by curly braces and percent signs {% raw %}`{%  %}`{% endraw %}, e.g. {% raw %}`{% if page.title %}{{ page.title }}{% endif %}`{% endraw %}

Liquid offers a lot of power and flexibility to mold your website--and given its focused purpose and small size, it is a great language to learn about programing concepts.

### Edit about.md

Let's edit your About page to make use of all the new features we added:

- On your repo home page click the filename "about.md", which will bring you to the page for that file.
- On the upper right corner of the file click the "pencil" icon to start editing.
- Edit your about.md file trying out the following options:

<div class="ml-4" markdown="1"> 

#### Front Matter

First, change the YAML front matter to use our new "dark" layout.
You can also define a new variable in the front matter block.

```
---
layout: dark
title: About
example: This is an example value.
---
```

#### Use Liquid Variables 

Try using a Liquid variable in your Markdown content. 
Objects defined in `_config.yml` will be named `site.variable_name`, e.g. {% raw %}`{{ site.title }}`{% endraw %}. 
Objects defined in the front matter will be prefixed with `page.`, e.g. {% raw %}`{{ page.title }}`{% endraw %}.
When the page is built, Liquid will swap out the variable name with the value. 
This allows you to configure core values and reuse them to maintain consistency.

```{% raw %}
This page describes the amazing {{ site.title }} by {{ site.author.name }}.
{{ page.example }}
{% endraw %}
```

#### Add Liquid Include

Insert your "big-cat" include:

```
{% raw %}{% include big-cat.html %}{% endraw %}
```

</div>

- Fill in your "commit message" and click the green "Commit changes" button.
- Wait for the green check showing successful build, then refresh your about page to see how it going!

Here is my complete About at this point for reference: 

```
---
layout: dark
title: About
example: This is an example value.
---

{% raw %}This page describes the amazing {{ site.title }} by {{ site.author.name }}.
{{ page.example }}

{% include big-cat.html %}
{% endraw %}
## About About Pages

The About page is a common convention found on websites.
It is your opportunity to let us know all the details "about" your project:

- focus and topic area
- people involved
- code and projects used

```

### Advanced Liquid

It is *very important* to display our animal data, so let's jump into some more advanced Liquid.
Start editing `about.md` again:

- On "about.md", click the "pencil" icon to start editing.
- Edit your about.md file trying out the following options:

<div class="ml-4" markdown="1"> 

#### For Loop

First, we need to access the information in `_data/animals.csv`. 
Jekyll exposes all the data files at `site.data.` + the filename without the extension, i.e. our data will be at `site.data.animals`.

Second, we need a Liquid [for loop](https://shopify.github.io/liquid/tags/iteration/){:target="_blank" rel="noopener"} to iterate over each line in the CSV.
This is set up like:

```{% raw %}
{% for animal in site.data.animals %}

{% endfor %}{% endraw %}
```

Now inside the for loop we will need to access the individual values from each CSV column. 
This is done by adding the column name to the iteration variable using dot notation, e.g `animal.name` or `animal.size`. 
We can use these variables in Markdown to set up a template inside the loop. 
For example, we could create a list:

```{% raw %}
{% for animal in site.data.animals %}
- The {{ animal.name }} is a {{ animal.size }} animal.
{% endfor %}{% endraw %}
```

This Liquid will retrieve the data from `animals.csv`, and for each row of the CSV fill in the template using the values in columns "name" and "size".

#### If Statement

Maybe we want another list with some special formatting for large animals.
We can use a Liquid [if statement](https://shopify.github.io/liquid/tags/control-flow/){:target="_blank" rel="noopener"} for this enhancement: 

```{% raw %}
{% for animal in site.data.animals %}
{% if animal.size == "large" %}- <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
{% else %}- <small>{{ animal.name }}</small>
{% endif %}
{% endfor %}{% endraw %}
```

In this loop, each row will be checked by the "if" condition.
If the value in the CSV column "size" is "large", then our template with `strong` style will be applied making the animal "name" bold and colored.
If not, then the animal "name" will be in small text.

Always be sure to close your If with `{% raw %}{% endif %}{% endraw %}`!

#### Where Filter

Liquid has many options to transform and manipulate data using filters.
A common use is to subset the items in your data. 

For example, we need a list of only the small animals.
First, we set up a new object using the [Assign tag](https://shopify.github.io/liquid/tags/variable/){:target="_blank" rel="noopener"}.
Then we can apply a [Where filter](https://shopify.github.io/liquid/filters/where/){:target="_blank" rel="noopener"} to select only the rows with "small" in the size column. 

```{% raw %} 
{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for animal in small_animals %}
- {{ animal.name | upcase }}
{% endfor %}{% endraw %}
```

</div>

- Fill in your "commit message" and click the green "Commit changes" button.
- Wait for the green check showing successful build, then refresh your about page to see the new additions!

Here is my final About page for reference:

```
---
layout: dark
title: About
example: This is an example value.
---

{% raw %}This page describes the amazing {{ site.title }} by {{ site.author.name }}.
{{ page.example }}

{% include big-cat.html %}

## About About Pages

The About page is a common convention found on websites.
It is your opportunity to let us know all the details "about" your project:

- focus and topic area
- people involved
- code and projects used

## List of Animals

{% for animal in site.data.animals %}
- The {{ animal.name }} is a {{ animal.size }} animal.
{% endfor %}

## Large Animals are Better

{% for animal in site.data.animals %}
{% if animal.size == "large" %}- <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
{% else %}- <small>{{ animal.name }}</small>
{% endif %}
{% endfor %}

## List of Small Animals

{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for animal in small_animals %}
- {{ animal.name | upcase }}
{% endfor %}

{% endraw %}
```

-------------

{% capture reference %}
- [Jekyll's Liquid docs](https://jekyllrb.com/docs/liquid/){:target="_blank" rel="noopener"} (Note: Jekyll provides some enhancements to Liquid that are not part of the standard spec)
- [Liquid documentation](https://shopify.github.io/liquid/){:target="_blank" rel="noopener"} (Note: these Liquid docs are for the most basic version. Some enhanced features are described in the [Shopify Liquid Reference](https://shopify.dev/docs/themes/liquid/reference){:target="_blank" rel="noopener"}, however, these docs are focused on the Shopify platform and may not apply to Jekyll's implementation)

{% endcapture %}
{% include card.html text=reference header="Reference" %}
