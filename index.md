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

Create a directory in `~/journal-hugo/content/` to hold the tutorials in one nice location.

    cd content/
    mkdir toots

### make a repository to hold the new page

You should make repositories for every text file you care about.  In this case, do not make it in ~/journal-hugo/content/toots because that is where the submodule will be.  Just make it in ~/whatever

    git remote add origin git@github.com:thunderrabbit/add-tutorial-to-a-hugo-site.git
    git push origin master

http://lmgtfy.com/?q=get+started+with+git to get started

### add the new repository as a submodule

    cd ~/journal-hugo/
    git submodule add git@github.com:thunderrabbit/add-tutorial-to-a-hugo-site.git content/toots/add-tutorial-to-hugo-site

### add content to the repository

    cd toots/add-tutorial-to-hugo-site/
	nano index.md

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
