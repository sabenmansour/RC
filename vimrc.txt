
"Activation de la numerotation des lignes
set number

" Activation de la coloration syntaxique
syntax enable

" Configuration de l'indentation
set tabstop=4             " Largeur d'une tabulation
set softtabstop=4         " Nombre d'espaces pour une tabulation
set shiftwidth=4          " Largeur de l'indentation lors de l'auto-indentation
set expandtab             " Convertit les tabulations en espaces

" Rechercher pendant la saisie
set incsearch
set hlsearch

" Activer la complétion automatique
set wildmenu
set wildmode=full

" Activer la recherche insensible à la casse
set ignorecase
set smartcase

" Activer la souris (pour les interfaces graphiques)
set mouse=a

" Activer la ligne de commande dans le bas de l'écran
set cmdheight=2

" Activer le presse-papiers système (clipboard)
set clipboard=unnamedplus

" Enregistrement automatique des fichiers modifiés
set autowrite

" Utiliser la touche Tab pour la complétion
inoremap <expr> <Tab> pumvisible() ? "\<C-n>" : "\<Tab>"

" Définir un raccourci pour enregistrer le fichier
nnoremap <leader>s :w<CR>

" Définir un raccourci pour ouvrir le gestionnaire de plugins
nnoremap <leader>vp :PluginList<CR>

" Définir un raccourci pour le redémarrage de Vim
nnoremap <leader>vr :source ~/.vimrc<CR>

" Installer les plugins avec vim-plug
call plug#begin('~/.vim/plugged')
Plug 'tpope/vim-sensible'
Plug 'scrooloose/nerdtree'
Plug 'vim-airline/vim-airline'
Plug 'majutsushi/tagbar'
Plug 'ctrlpvim/ctrlp.vim'
Plug 'junegunn/fzf'
Plug 'junegunn/vim-plug'
Plug 'ycm-core/YouCompleteME'
Plug 'Stirver/ultisnips'
Plug 'vim-syntastic/syntactic'
Plug 'airblade/vim-gitgutter'
Plug 'tpope/vim-commentary'
Plug 'tpope/vim-surround'
Plug 'jiangmiao/auto-pairs'
Plug 'honza/vim-snippets'
Plug 'dense-analysis/ale'



" Ajoutez d'autres plugins ici
call plug#end()

" Configuration Tagbar
nmap <F8> :TagbarToggle<CR>
let g:tagbar_autofocus = 1
let g:tagbar_width = 30

" Configurations pour les plugins
" NERDTree
map <C-n> :NERDTreeToggle<CR>

let NERDTreeQuitOnOpen = 1

" Vim Airline
"let g:airline_theme = 'default'

" Configuration spécifique à un langage
" Exemple pour Python
autocmd FileType python setlocal et sts=4 sw=4

" Configuration spécifique au markdown
" Exemple pour Markdown
autocmd FileType markdown setlocal spell spelllang=en_us

" Désactiver la création de fichiers de sauvegarde
set noswapfile
set nobackup
set nowritebackup

" Désactiver les fichiers temporaires
set noshowcmd

" Désactiver la création d'un fichier de historique
set history=0

" Désactiver la sauvegarde automatique
set noshowmatch
set noshowmode

" Désactiver les sons d'alerte
set noerrorbells
set novisualbell

" Activer les raccourcis pour copier et coller dans le presse-papiers
vmap <C-c> "+y
nmap <C-v> "+gP

" Sauvegarder la position du curseur
au BufReadPost * if line("'\"") > 0 && line("'\"") <= line("$") | execute "normal! g'\"" | endif
" Activation de la complétion automatique de mots
set completeopt=menuone,menu,longest

" Activation de la visualisation des espaces et des tabulations
set list
set listchars=tab:→\ ,trail:·

let g:tagbar_ctags_bin = '/usr/bin/ctags'
