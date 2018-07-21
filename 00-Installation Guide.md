---
publisher:  My Press
rights: © 2007 John Smith, CC BY-NC
title: 'Paper Authoring Course - Installation Guide'
subtitle: 'The subtitle of the book'
author: 'Alan Rynne'
date: 'July 2018'

documentclass: paper
classoption: 
toc: true
loc: true
lot: true
toc-depth: 3
---
# Installation Guide

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

## Text Editor

You could use any text editor to write your research paper, but in our case we are going to use Visual Studio Code.

VSC is a boiled down version of Visual Studio that is perfect for writing simple Python and C# scripts, but also amazingly good at Markdown syntax.

> Download Visual Studio Code at: [https://code.visualstudio.com/](https://code.visualstudio.com/)

Other **VERY** good text editors are *SublimeText* and *Atom*, they all have a very similar design and behaviour; and you will find most of the functionality can be extended to your needs via packages/extensions, no matter the text editor you choose.

We will also be making heavy use of VSC's extensions. You can install them directly from visual studio by pressing `CMD+SHIFT+X` on Mac or `CTRL+SHIFT+X` on Windows.

Search and install the following extensions:

* **Markdown All In One** - by Yu Zhang
* **Markdown Footnotes** - by Matt Bierner
* **Markdown Preview Enhanced** - by Yiyi Wang
* **markdownlint** - by David Anson
* **Python** - by Microsoft (this one might come pre-installed)
* **RainbowCSV** - by mechatroner (CSV colouring)
* **vscode-pandoc** - by DougFinke (Research Paper PDF rendering through VSC)
* **vscode-pdf** - by tomoki1207 (Visualize PDF without leaving VSC)

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
 3. `miktex` - Technically NOT an extension, this is the LaTex language renderer that pandoc uses under the hood.

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

Now that you got everything installed, it's time to open ***Visual Studio Code*** and start writing! But first, head to the next section to find out how to [setup Visual Studio Code](#)
