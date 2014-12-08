Vim on Windows 
========================
This is mostly intended as a note to myself, but might be useful to anyone who have trouble with Cygwin. I found instructions and help on these topics to be sparse and sometimes difficult to find, thus i decided to compile them in this handy document. This file describes how I set up my programming environment in windows 8 using the following:
* **Cygwin** with the mintty terminal
* **Vim** Custom vimrc, Pathogen and some useful plugins
* **Solarized** color palette for both vim and mintty
* **Sourcepro font**

Vim Plugins:
* **Neocomplete**
* **Ultisnips**
* **Julia-vim**

This is more a collection of links and notes if some part of an installation turned out to be trick in Cygwin, install instructions will be in the links.

## Cygwin
Get [latest version](https://cygwin.com/install.html), mintty should be included. During the Cygwin installation remember to tick of Vim as a package to be installed. The installer can be run again to update Cygwin or install new packages.

A few useful things one can install this way:
* **Vim**
* **gcc**
* **tex**
* **Lua interpreter** Needed for Neocomplete
* **Python interpreter** Needed for Ultisnips

## [Vimrc](http://amix.dk/vim/vimrc.html)
Copied Amir Salihefendics vimrc and made some minor additions.

## [Solarized](http://ethanschoonover.com/solarized)
A nice color palette, need to be installed separately for vim and mintty:
* **Vim**: https://github.com/altercation/vim-colors-solarized
* **Mintty**: https://github.com/mavnn/mintty-colors-solarized 

Even thought you only want Solarized in Vim, iff you use Vim in terminal mode, you will need the palette colors in the terminal as well.

## [Sourcepro font](https://store1.adobe.com/cfusion/store/html/index.cfm?event=displayFontPackage&code=1959)
* **Download** https://github.com/adobe-fonts/source-sans-pro/releases
* **Install instructions** http://www.adobe.com/products/type/install-instructions.html

## [Pathogen](https://github.com/tpope/vim-pathogen)
Curl is mentioned in the installation, disregard that. Just git clone in the '~/.vim' folder

## Vim Plugins
With pathogen installed, any plugins can easily be installed by cloning them into the '~/.vim/bundle' folder.

###[neocomplete](https://github.com/Shougo/neocomplete.vim)
Require vim with Lua, this is included in Cygwin
type 'vim --version' and there should be '+lua/dyn' in the list. Check in vim by typing: ':echo has("Lua")' should return a 1.
If 0 is returned, check that you selected the Lua interpreter when installing Cygwin
Add 'let g:neocomplete#enable_at_startup = 1' to the .vimrc

###[UltiSnips](https://github.com/SirVer/ultisnips)
Require vim with Python, this is also included in Cygwin, and can be checked similarly to checking for Lua.
In the 'vim --version' list there should be a '+' in front of 'python/dyn'. Check if python works by typing ':py print "anything"' in vim.

UltiSnips come without any default snips installed. Default snips can be found [here](https://github.com/honza/vim-snippets)
