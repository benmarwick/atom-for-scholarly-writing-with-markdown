---
csl: chicago-author-date.csl
bibliography: bibliography.bib
---

# Quick guide to scholarly writing in Markdown with Atom

This is an example markdown document with some details about how to do scholarly writing in Markdown using Atom.

Download and install atom from [https://atom.io/](https://atom.io/)

After opening Atom, install these packages into Atom by pressing `Ctrl` + `,`  then click on 'Install',  then enter these package names one by one, and click 'install' for each package:

- [autocomplete-en-en](https://atom.io/packages/autocomplete-en-en)
- [autocomplete-bibtex](https://atom.io/packages/autocomplete-bibtex)
- [autosave](https://atom.io/packages/autosave) (Settings -> check the box to enable)
- [highlight-selected](https://atom.io/packages/highlight-selected)
- [language-markdown](https://atom.io/packages/language-markdown)
- [linter-retextjs](https://atom.io/packages/linter-retextjs)
- [markdown-preview-enhanced](https://atom.io/packages/markdown-preview-enhanced)
- [pandoc-convert](https://atom.io/packages/pandoc-convert)
- [platformio-ide-terminal](https://atom.io/packages/platformio-ide-terminal) (`Ctrl` + \` to show/hide)
- [wordcount](https://atom.io/packages/wordcount) (Settings -> turn it on after installing)
- [zotero-picker](https://atom.io/packages/zotero-picker)

Outside of Atom, you will need to install:

- [Zotero](https://www.zotero.org/)
- [Zotero-better-bibtex](https://retorque.re/zotero-better-bibtex/installation/)
- [Git](https://git-scm.com/)

## Adding citations into the markdown text

There are two easy ways to add a citation:

1. Assuming that you have a `.bib` file in the same directory as the `.md` file, and that file has details in it, then in your Markdown document, type `[` then `@` and then the first few characters of the bibtex key, and choose which item to autocomplete, like this:  `[@marwick_computational_2016]`

2. Or, when writing your `.md` file, press `Alt` + `z` to get the Zotero search bar to pop up. Then type in the search bar and choose the item you want. Press `Enter` and you'll get a bibtex key like this in your text: `@marwick_computational_2016` You will still need to paste the full bibtex record into your local `.bib` file.

Look at the YAML front matter of this file to see how to link your `.bib` file to your `.md` file, it should be something like this:

```
---
csl: chicago-author-date.csl
bibliography: bibliography.bib
---
```

You need both of these files in the same directory as your `.md` file. The `.csl` file sets the style of your in-text citations and the items in the reference list. We can get different ones from here: <https://github.com/citation-style-language/styles> (be sure to download the raw, plain text file, not the website). The `.bib` is one you make by putting the full bibliopgraphic details from your Zotero library into this `.bib` file that lives with your `.md` file.

## Citation Syntax

With minor modifications we can get all the usual configurations of citations in our sentences (from [RStudio](https://rmarkdown.rstudio.com/authoring_bibliographies_and_citations.html)):

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

We're using [Git](https://git-scm.com/) for version control of our documents.

You can keep track of your Git database by clicking on the "Git" icon on the far right of the lower status bar. You can do a commit from that button.

Go to GitHub and create a new repository and add it as a remote to your project's Git repository. Then you can push from Atom.

### References

### Further reading

- <http://u.arizona.edu/~selisker/post/workflow/>
- <https://programminghistorian.org/en/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown>
- <http://plain-text.co>
- <https://the-javascripting-english-major.org/1-environment>
- <https://discuss.atom.io/t/using-atom-for-academic-writing/19222>
- <https://hackernoon.com/lint-lint-and-away-linters-for-the-english-language-70f4b22cc73c>
- Other fun Atom packages to explore: <https://atom.io/users/benmarwick/stars>
