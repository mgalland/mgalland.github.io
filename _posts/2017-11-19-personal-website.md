---
layout: post
author: Marc Galland
date: 2017-11-19
permalink: /first-post/
---

# Making your personal website
As I was willing to set-up a personal website for a while, I decided to give it a go following the nice example of [Sarah Stevens](http://sarahlrstevens.info/) and based on the [Jekyll now template](https://github.com/barryclark/jekyll-now).

There are a few installation requirements on your local machine to version control your website and being able to preview it locally. 

## Ruby setup
You need to have a working Ruby on your system. You can use **rbenv** to install and manage our Ruby versions.

1.  To do this, run the following commands in your Terminal: ``brew install rbenv ruby-build``
2.  Add rbenv to bash so that it loads every time you open a terminal ``echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile``. You can activate it with ``source ~/.bash_profile`` 
3.  Install Ruby: 
  * ``rbenv install 2.4.2``
  * ``rbenv global 2.4.2``
  * ``ruby -v``

## Jekyll installation 
This will install Jekyll together with the gems used by Github Pages to build your website.
``gem install github-pages``

## Git configuration 
Configurate your account.
*  ``git config --global color.ui true``
*  ``git config --global user.name "YOUR NAME"``
*  ``git config --global user.email "YOUR@EMAIL.com"``
Add some ssh keys (avoid password typing)
*  ``ssh-keygen -t rsa -C "YOUR@EMAIL.com"``
*  ``cat ~/.ssh/id_rsa.pub``
*  ``ssh -T git@github.com``

## Local Git/Github configuration
[Github documentation is here](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/)

# More resources
*  https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/
*  https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages