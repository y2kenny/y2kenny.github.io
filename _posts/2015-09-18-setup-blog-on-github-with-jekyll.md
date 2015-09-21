---
layout: post
title: Setup a blog on GitHub with Jekyll
published: true
comments: true
tags:
- blog
- jekyll
---

Jekyll is a static site generator designed for generating blog.  GitHub Pages support Jekyll natively.

<!--more-->

## GitHub setup

You essentially need to create a repository named \<username\>.github.io to host the blog.  You can find more information [here](https://pages.github.com).

## Local setup (using Ubuntu 14.04.2 LTS)

### Setup to use Jekyll

1. Install ruby-dev (Gem install of Jekyll install needs it to compile some native library)
   ```
   sudo apt-get install ruby-dev
   ```

2. Install Jekyll (-V for verbose)
   ```
   sudo gem install -V jekyll
   ```

### Additional setup

1. Install Pygments for syntax highlight

   ```
   sudo apt-get install python-pip
   sudo pip install pygments
   ```

### Setup the blog
* Initialize a local git repo

   ```
   mkdir <username>.github.io
   git init .
   git remote add origin https://github.com/<username>/<username>.github.io.git
   ```
* Find a Jekyll theme ([There](https://github.com/jekyll/jekyll/wiki/Themes) [are](http://jekyllthemes.org/) [many](https://github.com/poole/poole))
 * (I used [Lanyon](http://lanyon.getpoole.com/))

## Other notes

* Default markdown preprocessor seems to have [issues](https://github.com/jekyll/jekyll/issues/3724).
 * I used [redcarpet](https://github.com/vmg/redcarpet) instead:

```
sudo gem install redcarpet

#_config.yml
markdown: redcarpet
redcarpet:
  extensions: ["tables", "fenced_code_blocks"]
```

* To put tags on GitHub Pages without plugin, follow [these instructions](http://mrloh.se/2015/06/automatic-archives-for-jekyll-on-github-pages/).
