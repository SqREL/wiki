# Neovim

## Why?

Historical reasons. About 10 years ago i've tried vim and get used to it
so much, so every other software feels like a slow peace of crap.

## Config

```
let g:python_host_prog = '/usr/local/bin/python2.7'
let g:python3_host_prog = '/usr/local/bin/python3'

" This config will enable english language in vim.
" Otherwise the language for some reason will be your local
set langmenu=en_US
let $LANG = 'en_US'

"" ----------------------------------------------------------------------------
""
""
"" ===============================
"" | Packages                    |
"" ===============================
""
""
"" ----------------------------------------------------------------------------

" Initialize minpac package manager
packadd minpac
call minpac#init()

" Best and fastest fuzzy finder
set rtp+=/usr/local/opt/fzf
call minpac#add('junegunn/fzf.vim')

" Autocompletion
call minpac#add('Shougo/deoplete.nvim')
let g:deoplete#enable_at_startup = 1
call minpac#add('tbodt/deoplete-tabnine', { 'do': './install.sh' })

" Nerd Tree for project browsing
call minpac#add('scrooloose/nerdtree')
" Show changed files in nerd tree
call minpac#add('Xuyuanp/nerdtree-git-plugin')

" Mark changed lines of code
call minpac#add('airblade/vim-gitgutter')

" Add git support
call minpac#add('tpope/vim-fugitive')

" CLOJURE GOES HERE

call minpac#add('tpope/vim-fireplace')
call minpac#add('venantius/vim-eastwood')
call minpac#add('venantius/vim-cljfmt')

call minpac#add('morhetz/gruvbox')

" Programming tracker
call minpac#add('wakatime/vim-wakatime')

" Ruby codesmell analyzer
call minpac#add('rainerborene/vim-reek')

" Load packages right now
packloadall

"" ----------------------------------------------------------------------------
""
""
"" ===============================
"" | Global configuration        |
"" ===============================
""
""
"" ----------------------------------------------------------------------------

" Disable compatibity layer with VI
set nocompatible

let $NVIM_TUI_ENABLE_TRUE_COLOR = 1

" Turn on mouse support
set mouse=a

" Turn off backup files (SWP)
set nobackup
set nowritebackup
set noswapfile

" Autoread files when change brach on git
set autoread 

" Show line numbers
set number

" Show spaces and tabs
set list
set listchars=tab:▷⋅,trail:⋅,nbsp:⋅

" Visual separator
set colorcolumn=80

" Save undo between sessions
set undofile


" Set tab size
set tabstop=2
set shiftwidth=2
" Use ONLY spaces, not tabs
set expandtab
 " only even number of spaces 
 " (3 spaces + tab = 4 spaces, 2 spaces + tab = 4 spaces)
set smarttab
set nojoinspaces


" Use system clipboard
set clipboard=unnamedplus

" Ignore caseb when searching via vim
set ignorecase

" Setup background
set background=light

colorscheme onehalflight

"" ----------------------------------------------------------------------------
""
""
"" ===============================
"" | Key Bindings                |
"" ===============================
""
""
"" ----------------------------------------------------------------------------

" Shorthey for fuzzy finder
map <leader>t :FZF<CR>

" move between splits by tab
nnoremap <Tab> <C-w>w

" turn search highlight off
nnoremap <leader><space> :noh<cr>

" open NerdTree file browser
map <leader>o :NERDTreeToggle<cr>

" navigate through autocomplete menu (Deoplete)
inoremap <C-k> <C-Up>
inoremap <C-j> <C-Down>

" Turn on python3 
let g:python3_host_prog = '/usr/local/bin/python3'
```
