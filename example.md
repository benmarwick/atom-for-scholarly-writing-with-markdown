---
csl: chicago-author-date.csl
bibliography: bibliography.bib
---

# Quick guide to scholarly writing in Markdown with Atom

This is an example markdown document with some details about how to do scholarly writing in Markdown using Atom. You'll need these packages installed first:

- zotero-picker
- autocomplete-bibtex
- wordcount (Settings -> turn it on after installing)
- linter-write-good
- linter-just-say-no (say 'yes' to all prompts)
- autosave (Settings -> check the box to enable)
- markdown-writer
- markdown-preview-enhanced
- language-pfm
- pandoc-convert
- platformio-ide-terminal
- git-plus

Outside of Atom, you will need to install:

- [Zotero](https://www.zotero.org/)
- [Zotero-better-bibtex](https://retorque.re/zotero-better-bibtex/installation/)
- [Git](https://git-scm.com/)

## Adding citations into the markdown text

There are two easy ways to add a citation:

1. Assuming that you have a `.bib` file in the same directory as the `.md` file, and that file has details in it, then in your Markdown documner, type `[` then `@` and then the first few characters of the bibtex key, and choose which item to autocomplete, like this:  `[@marwick_computational_2016]`

2. Or, when writing your `.md` file, press `Control` + `z` to get the Zotero search bar to pop up. Then type in the seach bar and choose the item you want. Press `Enter` and you'll get a bibtex key like this in your text: `@marwick_computational_2016` You will still need to paste the full bibtex record into your local `.bib` file.

## Citation Syntax

With minor modifications we can get all the usual configurations of citations in our sentences:

`Blah blah [see @marwick_computational_2016, pp. 33-35; also @marwick2018standard, ch. 1].`

>Blah blah [see @marwick_computational_2016, pp. 33-35; also @marwick2018standard, ch. 1].

`Blah blah [@marwick_computational_2016, pp. 33-35, 38-39 and *passim*].`

>Blah blah [@marwick_computational_2016, pp. 33-35, 38-39 and *passim*].

`Blah blah [@marwick2018standard; @marwick_computational_2016].`

>Blah blah [@marwick2018standard; @marwick_computational_2016].

A minus sign (-) before the @ will suppress mention of the author in the citation. This can be useful when the author is already mentioned in the text:

`Marwick and Piilar Birch say blah [-@marwick2018standard].`

>Marwick and Piilar Birch [-@marwick2018standard] say blah

You can also write an in-text citation, as follows:

`@marwick2018standard says blah.`

> @marwick2018standard says blah.

`@marwick2018standard [p. 33] says blah.`

>@marwick2018standard [p. 33] says blah.


## Viewing citations when writing markdown

Go to Settings -> Packages -> markdown-preview-enhanced then look for the option 'Pandoc options: Commandline Arguments' and paste in this text: `--filter=pandoc-citeproc`

After this, when writing Markdown we can press `Control` + `shift`+ `m` and we'll see a panel with the citations processed correctly, for example, @marwick_computational_2016

## Convert Markdown to MS Word docx

To convert the Markdown document into a MS Word docx document we use the terminal (start the terminal with `Command` + `shift`+ `t`), check that the terminal in is the right directory (this will be fine if you are using an Atom project) and type in `pandoc -s example.md -o example.docx --filter pandoc-citeproc`

You should change the names of the `.md` and `.docx` files in that command to match your own files.

## Tracking changes and version Control

We're using [Git](https://git-scm.com/) for version control of our documents. In Atom, you need to install the git-plus package. After adding some text to your Markdown file, save it, then press `Control` + `shift`+ `p` to get the command palette, then type 'Git add all and commit', and click on the matching text.

Then you'll get a little window pop up, type in a brief commit message, then save (`Control` + `s`) and it will auto-close. You can also keep track of your Git database by clicking on the "Git" item on the far right of the lower status bar. You can do a commit from that button also.

Go to GitHub and create a new repository and add it as a remote to your project's Git repository. Then you can push from Atom. 



### References
