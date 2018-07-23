---
title: 'Part V: Creating Markdown Snippets'
subtitle: 'Making our Text Editor do all the hard work'
author: 'Alan Rynne'
date: '23/07/2018'
layout: post
gh-repo: alanrynne/scientific-paper-tutorial
gh-badge: [star, fork, follow]
---

So you finished the last two sections and you are probably thinking:

> SH+T!!
> Do I *REALLY* need to remember all this stuff? 
> Do I have to type it down every time?

The answer to both questions is **NO**.

## VSC Default Markdown Snippets

Visual Studio Code already comes with Markdown syntax functionality from the start, it is just not active.

You can tell VSC to *suggest* some text snippets to you while you write, which can do a couple of handy tricks:

> Writting `image` and pressing the `TAB` key will introduce for you the `![Caption](Link)` text string that will introduce an image in Markdown.
> It will also let you complete each field in order, and switch to the next one pressing `TAB` again.
> Once you are finished editing the fields, press `TAB` again to continiue writting.

The same behaviour applies to `link`, `code`, `italic` & `bold`,

In order to activate this functionality, the following options have to be inserted into your VSC User Settings (`CTRL+,` or `CMD+,`):

```json
    "[markdown]":  {
        "editor.quickSuggestions": true,
        "editor.suggestOnTriggerCharacters": true,
        "editor.acceptSuggestionOnEnter": "smart",
        "editor.snippetSuggestions": "top",
        "editor.wordBasedSuggestions": false,
      },
```

As you might realize, this specific configuration will only apply on Markdown files (.md or .markdown). You can do this with any language in your settings.

Go on and try the VSC Snippets behaviour, I'm sure you will find it very usefull.

## The BIG problem

The problem is that our combination of Markdown+Pandoc has A LOT more things going on:

1. Footnotes
2. Bibliography references
3. Image references
4. Table references
5. Equations

And as we say in Part III, each of them has a different notation, depending if you are applying a code to an figure, or referencing that figure inside a paragraph.

## The solution

The solution is creating ***our own custom snippets*** that will only apply to Markdown syntax.

You can access the snippets .json files following this steps:

1. Press `CTRL+SHIFT+P` which will open up the command line.
2. Write `Configure User Snippets` and press `ENTER`.
3. Select Markdown from the drop-down menu.
   
That's it! A new file named `markdown.json` should open up. Inside that file you will find an short explanation of how to create your own snippets. A more detailed explanation can be found [here](http://code.visualstudio.com/docs/editor/userdefinedsnippets).

For now, just copy and paste the following snippets **right before the last `}`** on the file and save it.

```json
 // Snippets for Markdown + Pandoc (won't work on normal Markdown)
  
	"Bib_Ref": {
        "prefix": "bib",
        "body": [
          "[@${1:Reference}]"
        ],
        "description": "Insert a bibliography reference"
	},
	
	"Footnote_Caption": {
        "prefix": "footnote",
        "body": [
          "[^${1:Code}]: ${2:Footnote_Text}"
        ],
        "description": "Insert footnote text"
	},

	"Footnote_Ref": {
        "prefix": "footref",
        "body": [
          "[^${1:Code}]"
        ],
        "description": "Insert reference to footnote"
	},
	
	"Figure_Ref": {
        "prefix": "figref",
        "body": [
          "[@fig:${1:Code}]"
        ],
        "description": "Insert reference to figure"
	},
	
	"Figure_Code": {
        "prefix": "figure",
        "body": [
          "![${1:Caption}](${2:File_Path}){#fig:${3:Code}}"
        ],
        "description": "Insert figure reference code"
	},

	"Table_Ref": {
        "prefix": "tref",
        "body": [
          "[@tbl:${1:Code}]"
        ],
        "description": "Insert reference to table"
	},
	
	"Table_Caption": {
        "prefix": "tcap",
        "body": [
          ": ${1:Caption} {#tbl:${2:Code}}"
        ],
        "description": "Insert table caption with ref code"
	},

	"Equation_Ref": {
        "prefix": "eqref",
        "body": [
          "[@eq:${1:Code}]"
        ],
        "description": "Insert reference to equation"
	},
	
	"Equation": {
        "prefix": "eq",
        "body": [
          "$$${1:Equation}$$ {#eq:${2:Code}}"
        ],
        "description": "Insert equation with ref code"
	},

  "Math_Symbol": {
        "prefix": "symbol",
        "body": [
          "$\\\\${1:Math_Symbol}$"
        ],
        "description": "Insert inline Latex character"
  },

  "ToDo-Task": {
        "prefix": "task",
        "body": [
          "- [ ] ${1:Task}"
        ],
        "description": "Insert a new To-Do task"
  },

  "Comment": {
        "prefix": "cmnt",
        "body": [
          "[${1:Code}]: # (${2:Comment})"
        ],
        "description": "Insert a new comment"
  },

  "Pandoc-Definition": {
        "prefix": "def",
        "body": [
          "${1:Term}\n: ${2:Definition}"
        ],
        "description": "Insert a new term definition"
  },
```

Once you completed this step, you should have available the following snippets:

1. `bib` will insert a Bibliography reference
2. `figure` will insert an image with reference code
3. `figref` will insert a figure reference in a paragraph
4. `footnote` will insert a new footnote text.
5. `footref` will insert a footnote reference in a paragraph
6. `tcap` will insert a table caption wiht reference code
7. `tref` will isert a table reference in a paragraph
8. `eq` will insert an equation with reference code (this equation will ocuppy the whole line, to insert an equation inside text use `$$ $$`.)
9. `eqref` will isert a reference to an equation
10. `symbol` to insert a LaTeX symbol inside text (I created this to accelerate writing simple simbols like alpha or epsilon.)
11. `task` is a special one: It is only to create a quick task list. *THIS IS NOT COMPATIBLE WITH PANDOC!!*
12. `cmnt` will insert a comment. A comment will not appear in your final document, but its like any other reference: it needs a unique code to identify it.
13. `def` for pandoc definitions: Used to formulate theorems, problems & propositions in a scientific publicaiton.

This is all for now. They could obviously be improved and you are welcome to do so! If you do, I would love to hear about it!

By now, you should be more than ready to tackle most of the *inconveniences* of writing in Markdown, and you should be able to output a formated version of your paper that is *nearly*, if not **completely**, ready for publishing.