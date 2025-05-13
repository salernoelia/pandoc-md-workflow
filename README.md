# Pandoc Markdown Workflow

Workflow to use Markdown and Pandoc with LaTeX and BibTeX for writing.

## Rendering

```sh
pandoc text_simple.md --citeproc --pdf-engine=pdflatex -o output.pdf
```

or use the pandoc render function in VSCode within the command-palette.

## Multiple Files

When working with multiple files use cat to merge.

```sh
cat text_split_1.md text_split_2.md > text_split_merged.md
```

# Setup

### **Install Commands**

```sh
brew install pandoc
brew install basictex
brew install zotero                # or install from https://www.zotero.org/
brew install --cask visual-studio-code
brew install gh
brew install git

echo 'export PATH="/Library/TeX/texbin:$PATH"' >> ~/.zprofile
source ~/.zprofile
```

### **Zotero + BetterBibTeX**

1. Open Zotero
2. Install [BetterBibTeX](https://retorque.re/zotero-better-bibtex/)
3. Set up automatic `.bib` export to your note folder:

   - Right-click collection → _Export Collection_
   - Choose _BetterBibTeX_ format
   - Enable _Keep updated_

![](/images/zotero-better-bibtex.png)

## Plugins in VSCode

![](/images/pandoc-citer-plugin.png)
![](/images/markdown-plugin.png)
![](/images/pandoc-plugin.png)
![](/images/pdf-plugin.png)
