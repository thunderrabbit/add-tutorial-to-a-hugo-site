---
title: one way to create new pages in hugo
tags: tutorials
author: Rob Nugen
date: 2015-12-06T19:14:40+09:00
---

### note

The root of my hugo site is in `~/journal-hugo/`.  That's the directory
that has the `config.toml` file, and the `content/` directory where
all the source data goes.  My source data includes multiple
submodules, and we'll be making a new one of those today.

### make a directory to hold everything

Create a directory in `~/journal/content/` to hold the tutorials in one nice location.

    $ cd content/
    $ mkdir toots

### make a repository to hold the new page

You should make repositories for every text file you care about.

http://lmgtfy.com/?q=get+started+with+git to get started

### add the new repository as a submodule

    $ git submodule add git@github.com:thunderrabbit/add-tutorial-to-a-hugo-site.git content/toots/add-tutorial-to-hugo-site

### add content to the repository

    $ cd toots/add-tutorial-to-hugo-site/
	$ nano index.md

### Add your page content to index.md

Edit `index.md` with your favorite text editor, and start with the YAML meta data:

    ---
    title: one way to create new pages in hugo
    tags: tutorials
    author: Rob Nugen
    date: 2015-12-06T19:14:40+09:00
    ---
    
    ### note
    
    The root of my hugo site is in `~/journal-hugo/`.  That's the directory

Add whatever you like as content below the front matter.

### Add index.md to the repository

    $ git add index.md
    $ git commit -m "First version of new page"
