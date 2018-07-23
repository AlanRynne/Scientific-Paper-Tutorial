---
title: 'Part I: Installation Guide'
subtitle: 'Everything you''ll need to succeed'
author: 'Alan Rynne'
date: '23/07/2018'
layout: post
gh-repo: alanrynne/scientific-paper-tutorial
gh-badge: [star, fork, follow]
---

Hi! Welcome to the ***Scientific Paper Tutorial***. In this short blog-series, you'll learn about the possibilities that Markdown syntax and the Pandoc library offer you to simplify your scientific writting workflow in order to concentrate purely on what's important: ***YOUR RESEARCH***.

This first chapter covers the installation process of all the different libraries and programs that we'll use in the next chapters. Note that you can find all of the content's of this course ready to download from this project's [Github Repository](http://github.com/alanrynne/Scientific-Paper-Tutorial).

Let's get started!!!

## Package managers

A package manager will manage the installation of all other necessary programs and libraries. This will be done through the **command/powershell** (Windows) or the **terminal** (Mac/Linux).

### Installing Chocolatey for Windows

If you are running windows, the best package manager right now is called ***Chocolatey***.

1. You can find out more at the [Chocolatey Official Website](https://chocolatey.org/)

2. For installation, please follow the [Installation Guide](https://chocolatey.org/install)

3. To search for any package available, you can visit [https://chocolatey.org/packages](https://chocolatey.org/packages)`

### Installing Homebrew for Mac

If you are running a Mac, installing 'homebrew' is quite straight-forward. Just paste the following command on the terminal and run it:

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
`

> You can also find out more at [their website](https://brew.sh) or search for available packages at [https://formulae.brew.sh/formula/](https://formulae.brew.sh/formula/).

### Usage

Once you have ***Chocolatey*** or ***Hombrew*** *up and running* you can easily install other packages by using the command `choco install PACKAGE_NAME` for Windows or `brew install PACKAGE_NAME` for Mac. *(changing `PACKAGE_NAME` for the name of the actual name of the package you wish to install.)*

## Python & pip

Now that we have `choco` or `brew` working, we need use install `python` and `pip` by copying and pasting the following commands on the terminal.

### Windows

* `choco install python2` to install Python 2.7
* `choco install pip` to install `pip` (the python package manager)

### Mac

* `brew install python2` to install Python 2.7
* `brew install pip` to install `pip` (the python package manager)

## Pandoc

Pandoc is a fantastic library for converting between a large list of markup document formats, such as `.docx`, `.pdf`, `html` or `epub`. It also manages references, citations, image numbering, templating and other fancy stuff.

 We will use `choco` or `brew` respectively to install `pandoc` on our computer. We will also be installing the following extensions:

 1. `pandoc-citeproc` (to handle bibliography citations)
 2. `pandoc-crossref` (to render image, table and equation references)
 3. `miktex` - Technically NOT an extension, this is the $\LaTeX$ language renderer that pandoc uses under the hood.

> Pandoc and Miktex will also allow you to write fancy mathematical notation with little effort. Such as:
> $$f(x)=a^m_i + b^n_j$$

### Windows

Copy and paste the following commands on your windows command shell:

* `choco install pandoc`
* `choco install pandoc-crossref`
* `choco install pandoc-citeproc`
* `choco install miktex`

### Mac

Copy and paste the following commands on your linux terminal:

* `brew install pandoc`
* `brew install pandoc-crossref`
* `brew install pandoc-citeproc`
* To install miktex on a mac you need to run
  * `brew tap miktex/miktex` and then
  * `brew install miktex`

> ### Miktex
> Just as a comment, MikTex is not a Pandoc extension. It is a program that installs the $\LaTeX$ language libraries that Pandoc uses to convert files. Sometimes, your default installation will come without some of the packages needed for a template and Pandoc will complain.  
> Most of the times, the solution is as easy as opening Miktex and searching for the missing package.

## Git

And finally, a ***source control package*** will help you maintain your sanity while writting/coding. In short terms, it keeps track of the changes on your files as you advance in your projects.

You can install it the same way as any other package.

### For widows

Copy and paste the following commands on your windows command shell:

`choco install git`

### For Mac

Copy and paste the following commands on your linux terminal:

`brew install git`

## Next steps

Now that you got everything installed, it's time to open ***Visual Studio Code*** and start writing!

But first, head to the next file to finish setting up everyting and print a test PDF to make sure.