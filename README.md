## Jasper

[![Build Status](https://travis-ci.org/biomadeira/jasper.svg?branch=master)](https://travis-ci.org/biomadeira/jasper)
[![Ruby](https://img.shields.io/badge/ruby-2.1.1-blue.svg?style=flat)](http://travis-ci.org/biomadeira/jasper)
[![Jekyll](https://img.shields.io/badge/jekyll-3.0.0-blue.svg?style=flat)](http://travis-ci.org/biomadeira/jasper)

This is a port of Ghost's default theme [Casper](https://github.com/tryghost/casper) for Jekyll inspired by [Kasper](https://github.com/rosario/kasper). 

You might well ask at this point why bother making a new Casper's clone? 
Although this is inspired by Kasper, there are several **additional** features which make this port closer 
to the original theme. Besides, I have recently updated it to match the current version of the theme.


## Live demo

[Jasper Live Demo](https://biomadeira.github.io/jasper)

[Casper's Original Here](https://demo.ghost.io)


## Screenshots

**Home page**
![home page](https://raw.githubusercontent.com/biomadeira/jasper/master/assets/images/jasper_screen1.png)

**Post page**
![post page](https://raw.githubusercontent.com/biomadeira/jasper/master/assets/images/jasper_screen2.png)

**Author page**
![author page](https://raw.githubusercontent.com/biomadeira/jasper/master/assets/images/jasper_screen3.png)

**Related posts page**
![tag page](https://raw.githubusercontent.com/biomadeira/jasper/master/assets/images/jasper_screen4.png)

**Tags page with opened sidebar**
![sidebar page](https://raw.githubusercontent.com/biomadeira/jasper/master/assets/images/jasper_screen5.png)

**404 page**
![related page](https://raw.githubusercontent.com/biomadeira/jasper/master/assets/images/jasper_screen6.png)

## Jasper theme includes

* Pagination
* Author page (New 07.02.2015)
* Tag page(s) (New 07.02.2015)
* 404 page (New 07.02.2015)
* Toggleable sliding sidebar (New 07.02.2015)
* Related posts view (New 30.10.2015)
* Tag description(s) (New 30.10.2015)
* Code Syntax Highlight (New 24.11.2015)
* Code Syntax Highlight with [highlight.js](https://highlightjs.org/) **(New 06.04.2016)**
* Rss updated to Jekyll 3.0 **(New 06.04.2016)** 
* Google Analytics tracking
* Author's profile with picture
* Disqus comments (not Ghost standard)

## How to use it

### Deployment

**Important:**  For security reasons, Github doesn't allow plugins (under _plugins/) when deploying with Github Pages. This means:

**1)** that we need to generate your site locally (more details below) and push the resulting HTML to a Github repository;

**2)** built the site with [travis-ci](https://travis-ci.org/) (with goodies from [jekyll-travis](https://github.com/mfenner/jekyll-travis)) automatically pushing the generated *_site/* files to your *gh-pages* branch.
 This later approach is the one I am currently using to generate the live demo.

For option **1)** simply clone this repository (*master branch*), and then run `jekyll serve` inside the directory. Upload the resulting *_site/* contents to your repository (*master branch* if uploading as your personal page (username.github.io) or *gh-pages branch* if uploading as a project page (as for the [demo](https://github.com/biomadeira/jasper/tree/gh-pages)).

For option **2)** you will need to set up travis-ci for your personal fork. Briefly all you need then is to change your details in *[\_config.yml](_config.yml)* so that you can push to your github repo. You will also need to generate a secure key to add to your *[.travis.yml](.travis.yml)* (you can find more info on how to do it in that file). Also make sure you read the documentation from [jekyll-travis](https://github.com/mfenner/jekyll-travis). This approach has clear advantages in that you simply push changes to your files and all the html files are generated for you. Also you get to know if everything is still fine with your site builds. Don't hesitate to contact me if you still have any issues (see below about issue tracking).

### Author pages

As discussed [here](https://github.com/biomadeira/jasper/issues/3), in order to properly generate author pages you need to rename the field *categories* in the front matter of every post to match that of your *username* as defined in the *[\_config.yml](_config.yml)* file.
This probably means that with a bit of hacking you could in principle generate multiple author blogs. Check this [link](https://github.com/biomadeira/jasper/issues/10) for more on working with multiple authors...

## Issues and contributing 

This install builds well with Ruby v2.1.1 and Jekyll v3.0.0. If you run into any problems please log them on the [issue tracker](https://github.com/biomadeira/jasper/issues).

Feel free pull-request your patches and fixes.

## Thanks 


Many thanks to the Ghost team for all the design work that allows to make this clone possible. Also many thanks to all contributors, that help keeping the project alive and updated :smile:


## Copyright & License

Copyright (C) 2015 - Released under the MIT License.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

