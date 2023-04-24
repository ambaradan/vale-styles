# Rocky Docs - Vale Styles

Project for creating custom Vocabularies for Markdown code analysis with Vale linter.

## Purpose of the project

Eliminate all Vale warnings such as:

> Use correct American English spelling. Did you really mean 'Rocky'?

To focus on the warnings most relevant to the content of the document.

### Requirements

- NvChad properly installed with the [Chadrc Template](https://docs.rockylinux.org/books/nvchad/template_chadrc/) provided by the developers.
- Git

## Installation

The installation is designed to be placed in the Neovim sharing folder `~/.local/share/nvim/`, this is to keep it hidden from the user's folders and to conform it to NvChad.

We first clone the repository in the Neovim share folder:

```bash
cd ~/.local/share/nvim/
git clone https://github.com/ambaradan/vale-styles.git
```

The repository contains the correctly configured `.vale.ini` file for both Vocabulary initialization and integration of custom Vocabs for Rocky documentation.

```text
StylesPath = ~/.local/share/nvim/vale-styles

Vocab = rockydocs, terminology

MinAlertLevel = suggestion

Packages = RedHat, alex

[*]
BasedOnStyles = Vale, RedHat, alex
```

copy the file to your home directory:

```bash
cp ~/.local/share/nvim/vale-styles/.vale.ini ~/.
```

and initialize Vocabularies:

```bash
~/.local/share/nvim/mason/packages/vale/vale sync
 SUCCESS  Downloaded package 'RedHat'                                                                 
 SUCCESS  Downloaded package 'alex'                                                                    
Downloading packages [2/2] ████████████████████████████████████████████████████████████████████████ 100% | 2s
```

Vocabularies will be downloaded to `~/.local/share/nvim/vale-styles/` and a **.gitignore** has been set up to prevent them from being shared by Git.

```text
~/.local/share/nvim/vale-styles/.gitignore
alex
RedHat
```

## NvChad setup


