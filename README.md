# Pandoc Markdown Workflow

Workflow to use Markdown and Pandoc with LaTeX and BibTeX for writing.

## Rendering

```sh
pandoc text_simple.md --citeproc --pdf-engine=pdflatex -o output.pdf
```

or use the pandoc render function in VSCode within the command-palette.

## Multiple Files

When working with multiple files use cat to merge.

```sh
cat text_split_1.md text_split_2.md > text_split_merged.md
```

# Setup MacOS

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

Here's the **equivalent Windows setup** using **Chocolatey** (or `winget` as an alternative where applicable):

---

## Setup Windows

### **Install Commands using Chocolatey**

First, open **PowerShell as Administrator** and run:

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Then install the tools:

```powershell
choco install pandoc -y
choco install miktex -y                     # TeX distribution for Windows
choco install zotero -y                     # or install manually from https://www.zotero.org/
choco install vscode -y
choco install gh -y                         # GitHub CLI
choco install git -y
```

---

### **Alternative with `winget`** (if you're on Windows 10 2004+ or Windows 11)

```powershell
winget install --id=Pandoc.Pandoc -e
winget install --id=MiKTeX.MiKTeX -e
winget install --id=Zotero.Zotero -e
winget install --id=Microsoft.VisualStudioCode -e
winget install --id=Git.Git -e
winget install --id=GitHub.cli -e
```

---

### **Post-Install Notes**

* `MiKTeX` will handle TeX dependencies similarly to `basictex` on macOS.

* Add MiKTeX to your `PATH` if it's not automatically done:

  ```powershell
  $env:Path += ";C:\Program Files\MiKTeX\miktex\bin\x64\"
  ```

* Verify installation:

  ```powershell
  pandoc -v
  git --version
  gh --version
  code --version
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

![](/images/pandoc-citer-plugin.png)ssh -T git@github.com
![](/images/markdown-plugin.png)
![](/images/pandoc-plugin.png)
![](/images/pdf-plugin.png)
