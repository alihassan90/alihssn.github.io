lablog: a jekyll template
==============================

This is a template for the static site generator [Jekyll](http://jekyllrb.com/). based on [Jekyll's default theme by jglovier](https://github.com/jglovier/jekyll-new). It adds functionality that targets at the use as a research log or notebook.

## What is a research log?

- write daily logs
- link information
- draft articles and essays
- build a knowledgebase

## What is Jekyll?


## Details

### Features:

- **Todo Lists** using the GitHub syntax `- [ ]`.
- **Tags** allow you to link posts of a certain topic, project or field of interest. Buttons for the **next and previous post** and automatic linking to **related posts** based on common tags facilitates browsing through posts.
- **Post Archive** is a chronological list of all posts, which is perfect for the use as a lab diary.  
- **Multi-authoring** for entire research groups due to an `author` tag in the front-matter
- **log your geolocation** with the `place` parameter
- **math equations** using [mathjax.org]() (renders $ \LaTeX $ syntax).

## Requirements

- Jekyll
- a convenient text editor (e.g. Geany, Notepad, Notepad++, Atom)

Recommended:

- git
- a Dropbox or GitHub account, or access to a webserver (for Deployment)

## Set-up

You can clone this repository to your computer and use `jekyll serve` to run it locally. It will be available in your browser under the URL `localhost:4000`.

## Use

### new posts

Just create a new file in the `_posts` directory with a filename of the scheme `YYYY-MM-DD-title.md` (file ending .md is for Markdown but [other filetypes are possible]()) and add a YAML front matter, which is two lines of three dashes each, with some information about your post in between:

    ---
    title: "My newest post"
    tags:
     - soup
     - conferences

    ---

    This is about soup, and conferences.



You do not necessarily need to enter any information. You could leave just an empty line between the dashes. But a title and tags make the log functional.

Posts are typically written in [Markdown](http://kramdown.gettalong.org/syntax.html) (Jekyll by default is using kramdown as a parser, but that can be configured).

### Pages

Information beyond posts, content that deserves a special spot on your log, is placed in pages. These are markdown files placed in the base directory with a simple filename (*not* the year-month-day name as for posts). Examples are `about.md`, `tags.md`, `index.html` and `archive.html`. They are rendered into static pages using a slightly different layout and are granted a spot in your header (the menu) at the top of the page.

#### Task lists

You can create new task list files by setting them up with a frontmatter that specifies

    ---
    layout: tasks
    title : Tasks

    ---

    ## Project 1

    - [ ] fix a bug in `soup.r`
    - [ ] write an [e-mail to Steve]()
    - [ ] write documentation
      - [ ] for `soup.r`
      - [x] soup recipe
    - [x] read [that paper about soup]()


of course you can change the title, but the layout *must* be set as `tasks`. You can write nested task lists, which opens wonderful possibilities for project management. Imagine that tasks can use links to connect to posts on the site, to e-mail addresses, to websites.


### Deployment

If you want to access the log from anywhere on the internet you will need one of the following solutions. For these you will have to specify the `url` and `baseurl`, as well as the target directory for generation `destination: `,  parameters in `_config.yml`. Just enter the values described below.  

#### Dropbox

In my opinion the perfect solution for a quick and semi-private deployment: Dropbox can serve a static site placed in the `/Public` folder. Just keep the log directory anywhere on your PC, but preferably in a private section of your Dropbox and specify `destination: ../../Public/lablog `, i.e. the relative path from your blog directory to the target directory. Then build your blog.

    jekyll build

Now, wait for the sync to happen and go to your Dropbox account online, navigate to your public directory, and there to the lablog directory. Right-click on the `index.html` file to get the public link. The root of this link (without `/index.html`) will be required for the next step:

Then set

    url "https://dl.dropboxusercontent.com"
    baseurl "u/xxxxxx/lablog"

Now build again and navigate in your browser to `https://dl.dropboxusercontent.com/u/xxxxxx/lablog/index.html`

Save this long, cryptic link as a bookmark or to load at browser start. For the future, all you need is to re-run the simple `jekyll build` command each time you updated a file.


#### GitHub pages

Advantage:

- free
- publishable URL
- automatic deployment
- version control (enforced)

Disadvantage:

- no plugins allowed
- no control over Jekyll parsing and version used

GitHub.com is providing free webhosting of static web content. Even better it  automatically deploys jekyll websites. You just have to create a branch called `gh-pages`,  push it with your updated content to GitHub and in an instant the site will be refreshed.

Specify:

    url "https://user.github.com"
    baseurl "lablog"



#### any other webserver

If you want to keep it truly private, the only solution will be a webserver.


## Customize

### Title and Author information

### About page

### version control

### License

### Theme color

### Rmarkdown or knitr reports

### Configure Jekyll



## Features to come:


- [ ] dashboard-like index page (first 4-6 posts, tag-list and categories)
- [ ] improving Todo list
  - [ ] filter for due date indicated by `due: XXXX-XX-XX`
  - [ ] Milestone tag `<hX> Milestone:`
  - [ ] switch: folding checked tasks of first level
  - [ ] switch: folding second level
  - [ ] folding of specific lists (button)
- [ ] category pages
  - [ ] make use of `site.categories[category]`  
  - [ ] read in of specific todo list, pages and posts
  - [ ] github api?
- [ ] easier linking between posts
  - [ ] hash tags: replace `#tag` with `<a href...>tag</a>`
  - [ ] how to use `{% post.url %}` for links
- [ ] adding a global search
- [ ] facilitate open research
  - [ ] provide Disqus hook??
  - [ ] adding CC license selector
  - [ ] move feeds link to footer
- [ ] sitemap.xml & robots.txt
- [ ] 404.html
- [ ] pdf-export template for pandoc
- [ ] manual for Rmarkdown or knitr

### known bugs:

[(please report at the issues page)]()


## License

The MIT License (MIT)

Copyright (c) 2014 Florian D. Schneider

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
