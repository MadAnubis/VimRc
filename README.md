# VimRc
"Vundel stuff

set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'gmarik/Vundle.vim'
" You Complete Me auto completer
Plugin 'Valloric/YouCompleteMe'


" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required


"New settings start!!!
"
"
"


"Colorscheme
"colorscheme something!!!
set background=dark "Dark background

syntax enable       "Enable syntax processing
set nocompatible    "No compatibility with vi
set encoding=utf-8  "UTF-8

set autoindent      "use indentation of previous line
set smartindent     "use intelligent indentation for C

"Tab config
set tabstop=4       "Number of spaces while opening file
set softtabstop=4   "Number of spaces while editing
set shiftwidth=4
set expandtab       "Tabs are spaces

" Make vim turn *off* expandtab for files named Makefile or makefile
" We need the tab literal
:autocmd BufNewFile,BufRead [Mm]akefile* set noexpandtab

" Make vim use 8 character tabstops and 
" recognize # as a start-of-comment token
" in assembly source files
:autocmd BufNewFile,BufRead *.s set tabstop=8 noexpandtab | syn match asmComment "#"

"UI config

set number          "Show line numbers
set showmode        "Show what mode we are in
set showcmd         "Show command in bottom bar
set cursorline      "Highlight cursor line
set scrolloff=10    "Visible 10 lines
filetype indent on  "Load filetype-specific indent files
set wildmenu        "Visual autocomplete for command menu
set lazyredraw      "Redraw only when needed
set showmatch       "Highlight matching {[()]}
set textwidth=80    "80 char 

"Searching config

set incsearch       "Search as characters are entered
set hlsearch        "Highlight matches

                    "Turn off highlight
nnoremap <leader><space> :nohlsearch<CR>
nnoremap + :noh

"Folding config

set foldenable      "Enable folding
set foldlevelstart=10 "Open most folds
set foldnestmax=10  "10 nested folds max
                    "Space to open fold
nnoremap <space> za

"Movement config

"Move to beginning/end of line 
nnoremap B ^
nnoremap E $

"HEX mode ON OFF

nnoremap m :%!xxd
nnoremap n :%!xxd -r

"Ypu Complete Me Config

let g:ycm_global_ycm_extra_conf ="~/.vim/bundle/YouCompleteMe/lang_config/c_config.py"
let &path = "/usr/lib/avr/include,/usr/include,./"
