---
title: Vim-MdToPdf
excerpt: A Vim plugin that converts Markdown documents to PDF files
header:
  teaser: /assets/images/vim-mdtopdf/icon.svg
---

A plugin for the Vim text editor to convert Markdown documents to PDF files. Supports entry of math using TeX.

## Installation

### Dependencies
- Python 3
- A version of Vim compiled with Python 3 support (run `vim --version` to check this, if you see `+python3`, you're good)
- The `lxml` Python module
- The `pyppeteer` Python module
- [WeasyPrint](https://weasyprint.org/)
- [Vim-Pandoc](https://github.com/vim-pandoc/vim-pandoc)

To install this plugin, run the following command in a terminal window (this assumes you have [Git](https://git-scm.com/) installed)
```shell
git clone https://github.com/ryangwsimmons/vim-MdToPdf.git ~/.vim/pack/plugins/start/vim-MdToPdf
```

If you have a preferred alternative method for installing Vim plugins, that should work too, however this is untested.

## Usage
When in a Markdown document, enter normal mode and type `:MdToPdf` to place a PDF of the Markdown document in the same directory, with the same name.

Running the command the first time may take a few minutes, depending on your internet connection, as a Chromium binary used to render JavaScript may need to be downloaded.

## Configuration
The plugin provides one global variable that you can redefine in your `.vimrc` file:

- `g:vim_mdtopdf_cssurl`: Used to define a path or URL for custom CSS (uses my own personal CSS file by default, which is a slight modification of the CSS that Microsoft uses for Markdown in VS Code.)
    * You can also use this CSS file to specify your paper size, if you want to use something other than Letter paper.
