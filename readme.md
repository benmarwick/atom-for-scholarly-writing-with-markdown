---
csl: chicago-author-date.csl
bibliography: bibliography.bib
---

# Quick guide to scholarly writing in Markdown with Atom

This is an example markdown document with some details about how to do scholarly writing in Markdown using Atom.

Download and install atom from [https://atom.io/](https://atom.io/)

After opening Atom, install these packages into Atom by pressing `Ctrl` + `,`  then click on 'Install',  then enter these package names one by one, and click 'install' for each package:

- [autosave](https://atom.io/packages/autosave) protects our work (Settings -> check the box to enable)
- [highlight-selected](https://atom.io/packages/highlight-selected) helps with editing
- [language-markdown](https://atom.io/packages/language-markdown) syntax highlighting
- [linter-retextjs](https://atom.io/packages/linter-retextjs) basic prose feedback
- [markdown-preview-enhanced](https://atom.io/packages/markdown-preview-enhanced) preview the document (`Ctrl` + `M` to show/hide)
- [pandoc-convert](https://atom.io/packages/pandoc-convert) installs Pandoc for us
- [platformio-ide-terminal](https://atom.io/packages/platformio-ide-terminal) easily use the terminal (`Ctrl` + \` to show/hide)
- [wordcount](https://atom.io/packages/wordcount) count the words (Settings -> turn it on after installing)

Outside of Atom, you will need to install:

- [Zotero](https://www.zotero.org/) and its [connector for Chrome](https://chrome.google.com/webstore/detail/zotero-connector/ekhagklcjbdpajgpjgmbionohlpdbjgc?hl=en) to collect and manage citations
- [Git](https://git-scm.com/) to keep track of different versions of our documents

## Adding citations into the markdown text

Assuming that you have a `.bib` file in the same directory as the `.md` file, and that file has details in it, then in your Markdown document, type `[` then `@` and then the first few characters of the bibtex key, and choose which item to autocomplete, like this:  `[@marwick_computational_2016]`

Look at the YAML front matter of this file to see how to link your `.bib` file to your `.md` file, it should be something like this:

```
---
csl: chicago-author-date.csl
bibliography: bibliography.bib
---
```

You need both of these files in the same directory as your `.md` file. The `.csl` file sets the style of your in-text citations and the items in the reference list. We can get different ones from here: <https://github.com/citation-style-language/styles> (be sure to download the raw, plain text file, not the website). The `.bib` is one you make by putting the full bibliographic details from your Zotero library into this `.bib` file that lives with your `.md` file.

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

Go to `Settings` -> `Packages` -> `markdown-preview-enhanced` and first, check the box for 'Use Pandoc parser', then, second, look for the option 'Pandoc options: Commandline Arguments' and paste in this text: `--filter=pandoc-citeproc`

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
