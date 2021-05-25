# 美im

### -- お前らのは微im --
m.oba present

---

ちなみにこの資料もvimで作りました!!!

---

## vimのバージョンを確認しよう

バージョンによってはプラグインが動かない場合があります

```shell
vim --version
```

>>>

```
VIM - Vi IMproved 8.2 (2019 Dec 12, compiled May 13 2020 16:28:49)
macOS 版
適用済パッチ: 1-750
Compiled by Homebrew
Huge 版 without GUI.  機能の一覧 有効(+)/無効(-)
+acl               -farsi             +mouse_sgr         +tag_binary
+arabic            +file_in_path      -mouse_sysmouse    -tag_old_static
+autocmd           +find_in_path      +mouse_urxvt       -tag_any_white
+autochdir         +float             +mouse_xterm       -tcl
-autoservername    +folding           +multi_byte        +termguicolors
-balloon_eval      -footer            +multi_lang        +terminal
+balloon_eval_term +fork()            -mzscheme          +terminfo
-browse            +gettext           +netbeans_intg     +termresponse
++builtin_terms    -hangul_input      +num64             +textobjects
+byte_offset       +iconv             +packages          +textprop
+channel           +insert_expand     +path_extra        +timers
+cindent           +ipv6              +perl              +title
-clientserver      +job               +persistent_undo   -toolbar
+clipboard         +jumplist          +popupwin          +user_commands
+cmdline_compl     +keymap            +postscript        +vartabs
+cmdline_hist      +lambda            +printer           +vertsplit
+cmdline_info      +langmap           +profile           +virtualedit
+comments          +libcall           -python            +visual
+conceal           +linebreak         +python3           +visualextra
+cryptv            +lispindent        +quickfix          +viminfo
+cscope            +listcmds          +reltime           +vreplace
+cursorbind        +localmap          +rightleft         +wildignore
+cursorshape       +lua               +ruby              +wildmenu
+dialog_con        +menu              +scrollbind        +windows
+diff              +mksession         +signs             +writebackup
+digraphs          +modify_fname      +smartindent       -X11
-dnd               +mouse             -sound             -xfontset
-ebcdic            -mouseshape        +spell             -xim
+emacs_tags        +mouse_dec         +startuptime       -xpm
+eval              -mouse_gpm         +statusline        -xsmp
+ex_extra          -mouse_jsbterm     -sun_workshop      -xterm_clipboard
+extra_search      +mouse_netterm     +syntax            -xterm_save
      システム vimrc: "$VIM/vimrc"
      ユーザー vimrc: "$HOME/.vimrc"
   第2ユーザー vimrc: "~/.vim/vimrc"
       ユーザー exrc: "$HOME/.exrc"
  デフォルトファイル: "$VIMRUNTIME/defaults.vim"
       省略時の $VIM: "/usr/local/share/vim"
コンパイル: clang -c -I. -Iproto -DHAVE_CONFIG_H   -DMACOS_X -DMACOS_X_DARWIN  -g -O2 -U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=1
リンク: clang   -L. -fstack-protector-strong -L/usr/local/lib -L/usr/local/opt/libyaml/lib -L/usr/local/opt/openssl@1.1/lib -L/usr/local/opt/readline/lib  -L/usr/local/lib -o vim        -lncurses -liconv -lintl -framework AppKit  -L/usr/local/opt/lua/lib -llua5.3 -mmacosx-version-min=10.15 -fstack-protector-strong -L/usr/local/lib  -L/usr/local/Cellar/perl/5.30.2_1/lib/perl5/5.30.2/darwin-thread-multi-2level/CORE -lperl -lm -lutil -lc  -L/usr/local/opt/python@3.8/Frameworks/Python.framework/Versions/3.8/lib/python3.8/config-3.8-darwin -lpython3.8 -framework CoreFoundation  -lruby.2.7
```

---

# vimの歴史

---

## 最も古いエディタって何でしょうか？

>>>

正解はパンチカードです．
<br>
![](../images/panchcard.jpg)

---

## 最も古いコンピュータエディタって<br>何でしょうか？

>>>

正解は`ed`というラインエディタです．  
このエディタは実は今でも使えます．  
しかし，ラインエディタなので，自分らが今使っているエディタという感じではありません．  

>>>

ターミナルで`ed`と打ち込んでみます．

`a`を入力すると挿入モードに入りテキストを入力ができます．  

挿入モードを終了したい場合は`.`を入力して`Enter`を押します．

>>>

ターミナルで`ed`と打ち込んでみます．

`a`を入力すると挿入モードに入りテキストを入力ができます．  

挿入モードを終了したい場合は`.`を入力して`Enter`を押します．

>>>

「w」の後にテキストを書き込むファイル名を入力してEnterキーを押すと，ファイルにテキストを保存できます．<br>
edを終了するには「q」を入力してEnterキーを押します．

---

edの後に「"editor for mortals"(人間のためのエディタ)」である「em」が開発され，1976年にemをベースとした「"extended ed"(edの拡張)」である「ex」が開発されます．
<br>exにはemの機能の他に，画面上にファイル全体を表示する「visual」モードが追加．これが「vi」の始まりで，その後1979年に，viはOSにコマンドとして導入されることになります．

>>>

viが登場して数年後，viのクローンが数多く登場したとのこと．その中のひとつが「Vi Improved」，つまり「Vim」です．

>>>

![](../images/110_m.png)

---

# ここからは HANDS ON

---

まずはVundleをインストール
<br>
```
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
<br>
ついでに

```
# mac
brew install ctag

# linux
sudo apt install ctag
```

---

```
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

Plugin 'VundleVim/Vundle.vim'

" 導入したいプラグインを以下に列挙
" Plugin '[Github Author]/[Github repo]' の形式で記入
"" git
Plugin 'airblade/vim-gitgutter'

"" vue.js
Plugin 'posva/vim-vue'

"" rails
Plugin 'tpope/vim-rails'

"" python
Plugin 'hdima/python-syntax'
Plugin 'heavenshell/vim-pydocstring'

"" html
" Plugin 'alvan/vim-closetag'
Plugin 'valloric/matchtagalways'

"" nerdtree
Plugin 'scrooloose/nerdtree'

"" autocomplete 
Plugin 'valloric/youcompleteme'
" Plugin 'neoclide/coc.nvim'

"" lightline
" Plugi 'itchyny/lightline.vim'
Plugin 'vim-airline/vim-airline'
Plugin 'vim-airline/vim-airline-themes'

"" icons
Plugin 'ryanoasis/vim-devicons'

"" tagbar
Plugin 'majutsushi/tagbar'

"" indentline
Plugin 'yggdroot/indentline'

"" docker 
Plugin 'ekalinin/dockerfile.vim'

"" filer
Plugin 'shougo/unite.vim'
Plugin 'shougo/vimfiler.vim'

"" comment out 
Plugin 'scrooloose/nerdcommenter'
Plugin 'joom/vim-commentary'

"" space + qr -> exec script
Plugin 'thinca/vim-quickrun'

"" linter
" Plugin 'dense-analysis/ale'

Plugin 'deton/jasegment.vim'
Plugin 'yuttie/comfortable-motion.vim'

Plugin 'iberianpig/tig-explorer.vim'

" snippet
Plugin 'sirver/ultisnips'
Plugin 'honza/vim-snippets'
Plugin 'shougo/neosnippet.vim'
Plugin 'shougo/neosnippet-snippets'

call vundle#end()
filetype plugin indent on
let mapleader="\<Space>"

"" ultisnip
" let g:UltiSnipsExpandTrigger="<tab>"
" let g:UltiSnipsJumpForwardTrigger="<tab>"
" let g:UltiSnipsJumpBackwardTrigger="<s-tab>"
" let g:UltiSnipsEditSplit="vertical"
let g:UltiSnipsExpandTrigger="<c-j>"
let g:UltiSnipsJumpForwardTrigger="<c-l>"
let g:UltiSnipsJumpBackwardTrigger="<c-h>"
let g:UltiSnipsEditSplit="vertical"

" let g:UltiSnipsSnippetDirectories=['UltiSnips',$HOME.'/dotfiles/vim/src/UltiSnips']
" " Plugin key-mappings.
" " Note: It must be "imap" and "smap".  It uses <Plug> mappings.
" imap <C-k>     <Plug>(neosnippet_expand_or_jump)
" smap <C-k>     <Plug>(neosnippet_expand_or_jump)
" xmap <C-k>     <Plug>(neosnippet_expand_target)
" let g:neosnippet#snippets_directory='~/.vim/bundle/neosnippet-snippets/neosnippets'
" " " SuperTab like snippets behavior.
" " " Note: It must be "imap" and "smap".  It uses <Plug> mappings.
" " "imap <expr><TAB>
" " " \ pumvisible() ? "\<C-n>" :
" " " \ neosnippet#expandable_or_jumpable() ?
" " " \    "\<Plug>(neosnippet_expand_or_jump)" : "\<TAB>"
" " smap <expr><TAB> neosnippet#expandable_or_jumpable() ?
" " \ "\<Plug>(neosnippet_expand_or_jump)" : "\<TAB>"
" " For conceal markers.
" if has('conceal')
"   set conceallevel=2 concealcursor=niv
" endif


"" youcompleteme
" let g:ycm_server_python_interpreter = '/Users/masashi/.pyenv/shims/python3.8.1'
" let g:ycm_python_binary_path = '/Users/masashi/.pyenv/shims/python3.8.1'
" let g:ycm_global_ycm_extra_conf = '~/.vim/plugged/YouCompleteMe/.ycm_extra_conf.py'
let g:ycm_auto_trigger = 1
let g:ycm_min_num_of_chars_for_completion = 1
let g:ycm_autoclose_preview_window_after_insertion = 1
inoremap <expr> <Tab> pumvisible() ? "\<C-n>" : "ᐅ"
" 補完表示時のEnterで改行をしない
inoremap <expr><CR>  pumvisible() ? "<C-y>" : "<CR>"
let g:ycm_key_list_stop_completion = ['<C-y>', '<Enter>']
let g:ycm_seed_identifiers_with_syntax = 1
let g:SuperTabDefaultCompletionType = '<C-n>'
let g:make = 'gmake'
if exists('make')
      let g:make = 'make'
endif

"" vim-airline
let g:airline_theme = 'solarized'
" let g:airline_theme = 'base16_gruvbox_dark_hard'
let g:airline#extensions#syntastic#enabled = 1
let g:airline#extensions#branch#enabled = 1
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tagbar#enabled = 1
let g:airline_skip_empty_sections = 1
let g:airline_powerline_fonts = 1

"" nerdtree
let g:NERDTreeChDirMode=2
let g:NERDTreeIgnore=['\.rbc$', '\~$', '\.pyc$', '\.db$', '\.sqlite$', '__pycache__']
let g:NERDTreeSortOrder=['^__\.py$', '\/$', '*', '\.swp$', '\.bak$', '\~$']
let g:NERDTreeShowBookmarks=1
let g:nerdtree_tabs_focus_on_files=1
let g:NERDTreeMapOpenInTabSilent = '<RightMouse>'
let g:NERDTreeWinSize = 30
let NERDTreeShowHidden=1
set wildignore+=*/tmp/*,*.so,*.swp,*.zip,*.pyc,*.db,*.sqlite
nnoremap <Leader>dir :NERDTreeTabsToggle<CR>
" autocmd BufWritePre * :FixWhitespace "必要なのか不明
autocmd VimEnter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif

"" quickrun
nnoremap <Leader>go :QuickRun<CR>
nnoremap <C-U>qr :QuickRun<CR>
let g:quickrun_config={'*': {'split': ''}}
let g:quickrun_config.cpp = {
            \   'command': 'g++',
            \   'cmdopt': '-std=c++11'
            \ }

"" vim-easy-align
xmap ga <Plug>(EasyAlign)
nmap ga <Plug>(EasyAlign)

"" vimshell
" nnoremap <Leader>sh :vertical terminal<CR>
nnoremap <Leader>sh :bo terminal ++rows=18<CR>
let g:vimshell_user_prompt = 'fnamemodify(getcwd(), ":~")'
let g:vimshell_prompt =  '$ '

"" syntastic
let g:syntastic_always_populate_loc_list=1
let g:syntastic_error_symbol='✗'
let g:syntastic_warning_symbol='⚠'
let g:syntastic_style_error_symbol = '✗'
let g:syntastic_style_warning_symbol = '⚠'
let g:syntastic_auto_loc_list=1
let g:syntastic_aggregate_errors = 1

"" Ale
let g:ale_sign_column_always = 1
let g:ale_sign_error = '>>'
let g:ale_sign_warning = '--'

"" vim-airline
" let g:airline#extensions#virtualenv#enabled = 1
" if !exists('g:airline_symbols')
"   let g:airline_symbols = {}
" endif
" if !exists('g:airline_powerline_fonts')
"   let g:airline#extensions#tabline#left_sep = ' '
"   let g:airline#extensions#tabline#left_alt_sep = '|'
"   let g:airline_left_sep          = '▶'
"   let g:airline_left_alt_sep      = '»'
"   let g:airline_right_sep         = '◀'
"   let g:airline_right_alt_sep     = '«'
"   let g:airline#extensions#branch#prefix     = '⤴' "➔, ➥, ⎇
"   let g:airline#extensions#readonly#symbol   = '⊘'
"   let g:airline#extensions#linecolumn#prefix = '¶'
"   let g:airline#extensions#paste#symbol      = 'ρ'
"   let g:airline_symbols.linenr    = '␊'
"   let g:airline_symbols.branch    = '⎇'
"   let g:airline_symbols.paste     = 'ρ'
"   let g:airline_symbols.paste     = 'Þ'
"   let g:airline_symbols.paste     = '∥'
"   let g:airline_symbols.whitespace = 'Ξ'
" else
"   let g:airline#extensions#tabline#left_sep = ''
"   let g:airline#extensions#tabline#left_alt_sep = ''
"   let g:airline_left_sep = ''
"   let g:airline_left_alt_sep = ''
"   let g:airline_right_sep = ''
"   let g:airline_right_alt_sep = ''
"   let g:airline_symbols.branch = ''
"   let g:airline_symbols.readonly = ''
"   let g:airline_symbols.linenr = ''
" endif

"" python
augroup vimrc-python
  autocmd!
  autocmd FileType python setlocal
        \ formatoptions+=croq softtabstop=4
        \ cinwords=if,elif,else,for,while,try,except,finally,def,class,with
augroup END

autocmd Filetype ipynb nmap <silent><Leader>b :VimpyterInsertPythonBlock<CR>
autocmd Filetype ipynb nmap <silent><Leader>j :VimpyterStartJupyter<CR>
autocmd Filetype ipynb nmap <silent><Leader>n :VimpyterStartNteract<CR>

"" move line/word
" nmap <C-e> $
" nmap <C-a> 0
" nmap <C-b> B
" imap <C-e> <C-o>$
" imap <C-a> <C-o>0
" imap <C-b> <C-o>B

""""""""""""""""""""""
" settings 
""""""""""""""""""""""

set virtualedit=all     " カーソルを文字が存在しない部分でも動けるようにする
" 入力モード中に素早くjjと入力した場合はESCとみなす
inoremap <silent> jj <Esc>

" ESCを二回押すことでハイライトを消す
nmap <silent> <Esc><Esc> :nohlsearch<CR>

"文字コードをUFT-8に設定
set encoding=UTF-8
set fenc=utf-8
set fileencoding=utf-8 " 保存時の文字コード
set fileencodings=ucs-boms,utf-8,euc-jp,cp932 " 読み込み時の文字コードの自動判別. 左側が優先される
set fileformats=unix,dos,mac " 改行コードの自動判別. 左側が優先される
set ambiwidth=double " □や○文字が崩れる問題を解決
" set guifont=SauceCodePro\ Nerd\ Font\ 11

" バックアップファイルを作らない
set nobackup
" スワップファイルを作らない
set noswapfile
" 編集中のファイルが変更されたら自動で読み直す
set autoread
" バッファが編集中でもその他のファイルを開けるように
set hidden
" 入力中のコマンドをステータスに表示する
set showcmd

" 見た目系
" 行番号を表示
set number
" 行末の1文字先までカーソルを移動できるように
set virtualedit=onemore
" インデントはスマートインデント
set smartindent
" ビープ音を可視化
" set visualbell
" ビープ音を鳴らさない
set vb t_vb=
" 括弧入力時の対応する括弧を表示
set showmatch
" ステータスラインを常に表示
set laststatus=0
" コマンドラインの補完
set wildmode=list:longest
" 折り返し時に表示行単位での移動できるようにする
nnoremap j gj
nnoremap k gk
" シンタックスハイライトの有効化
syntax on
colorscheme flattened_dark
" colorscheme rupza
" colorscheme molokai
" colorscheme miramare

set t_Co=256
set title
filetype on
highlight Normal ctermbg=none
highlight NonText ctermbg=none
highlight LineNr ctermbg=none
highlight Folded ctermbg=none
highlight EndOfBuffer ctermbg=none 

" Tab系
" 不可視文字を可視化(タブが「▸-」と表示される)
set list listchars=tab:\▸\-
" Tab文字を半角スペースにする
set expandtab
" 行頭以外のTab文字の表示幅（スペースいくつ分）
set tabstop=2
" 行頭でのTab文字の表示幅
set shiftwidth=2

" 検索系
" 検索文字列が小文字の場合は大文字小文字を区別なく検索する
set ignorecase
" 検索文字列に大文字が含まれている場合は区別して検索する
set smartcase
" 検索文字列入力時に順次対象文字列にヒットさせる
set incsearch
" 検索時に最後まで行ったら最初に戻る
set wrapscan
" 検索語をハイライト表示
set hlsearch
" ESC連打でハイライト解除
nmap <Esc><Esc> :nohlsearch<CR><Esc>
" 挿入モードからnormalモードまでを早くする
set ttimeoutlen=50

set backspace=indent,eol,start
set wildmenu " コマンドモードの補完
set history=5000 " 保存するコマンド履歴の数

if &term =~ "xterm"
  let &t_SI .= "\e[?2004h"
  let &t_EI .= "\e[?2004l"
  let &pastetoggle = "\e[201~"

  function XTermPasteBegin(ret)
    set paste
    return a:ret
  endfunction
  inoremap <special> <expr> <Esc>[200~ XTermPasteBegin("")
endif

" 入力モードでのカーソル移動
nnoremap あ a
nnoremap い i
nnoremap う u
nnoremap お o
nnoremap っd dd
nnoremap っy yy

" 補完ウィンドウの設定
set completeopt=menuone,noinsert

" rsenseでの自動補完機能を有効化
let g:rsenseUseOmniFunc = 1
" let g:rsenseHome = '/usr/local/lib/rsense-0.3'

" auto-ctagsを使ってファイル保存時にtagsファイルを更新
let g:auto_ctags = 1

" let g:lightline = {
"       \ 'colorscheme': 'solarized dark',
"       \ }

set laststatus=2
let g:airline_powerline_fonts = 2

" -- 大文字でも認識してほしい --
" 大文字 W で保存
command W w
" Q で quickrun 実行しないように
command Q q

" shortcut leader=Space
"" save
nnoremap <Leader>w :w<CR>
nnoremap <Leader>qqq :q!<CR>
nnoremap <Leader>eee :e<CR>
nnoremap <Leader>wq :wq<CR>
nnoremap <Leader>nn :noh<CR>

" emacs風な動き
inoremap <C-k> <Nop>
inoremap <C-j> <Nop>
inoremap <C-l> <Nop>
inoremap <C-h> <Nop>
imap <C-k> <Up>
imap <C-j> <Down>
imap <C-h> <Left>
imap <C-l> <Right>
"
" Split window
nmap sv :split<Return><C-w>w
nmap ss :vsplit<Return><C-w>w

" emacs風のキーバインド
" nnoremap <C-k> <Nop>
" nnoremap <C-j> <Nop>
" nnoremap <C-h> <Nop>
" nnoremap <C-l> <Nop>
" imap <C-k> <Up>
" imap <C-j> <Down>
" imap <C-h> <Left>
" imap <C-l> <Right>

" Move window
map sh <C-w>h
map sk <C-w>k
map sj <C-w>j
map sl <C-w>l

" resize window
map s= 5<C-w>+
map s- 5<C-w>-
map s, 5<C-w><
map s. 5<C-w>>

" Switch tab
nmap <S-Tab> :tabprev<Return>
nmap <Tab> :tabnext<Return>
nmap te :tabedit<Return>
nmap fe :VimFilerBufferDir<Return>
nmap ne :NERDTree<Return>
nmap ta :Tagbar<Return>

" -- commenter --
" Add spaces after comment delimiters by default
let g:NERDSpaceDelims = 1
" Use compact syntax for prettified multi-line comments
let g:NERDCompactSexyComs = 1
" Align line-wise comment delimiters flush left instead of following code
" indentation
let g:NERDDefaultAlign = 'left'
" Set a language to use its alternate delimiters by default
let g:NERDAltDelims_java = 1
" Add your own custom formats or override the defaults
let g:NERDCustomDelimiters = { 'c': { 'left': '/**','right': '*/' } }
" Allow commenting and inverting empty lines (useful when commenting a
" region)
let g:NERDCommentEmptyLines = 1
" Enable trimming of trailing whitespace when uncommenting
let g:NERDTrimTrailingWhitespace = 1
" Enable NERDCommenterToggle to check all selected lines is commented or not 
let g:NERDToggleCheckAllLines = 1
nmap <Leader>/ <Plug>NERDCommenterToggle
vmap <Leader>/ <Plug>NERDCommenterToggle

"" vimfiler
let g:vimfiler_as_default_explorer = 1
let g:vimfiler_safe_mode_by_default = 0
let g:vimfiler_enable_auto_cd = 0
let g:vimfiler_tree_leaf_icon = ''
let g:vimfiler_tree_opened_icon = '▾'
let g:vimfiler_tree_closed_icon = '▸'
let g:vimfiler_marked_file_icon = '✓'

vmap co gc<Return>
set clipboard=unnamed,autoselect

" 補完の色の設定
highlight Pmenu ctermfg=grey ctermbg=black
highlight PmenuSel ctermfg=blue ctermbg=red

"" + => increment
nnoremap + <C-a>
"" - => decrement
nnoremap - <C-x>

"" INSERTを表示しない
set noshowmode

nmap time i<C-R>=strftime("%H:%M:%S")<Return> >> 
nmap date i<C-R>=strftime("%Y-%m-%d")<Return> (<C-R>=[ "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" ][strftime("%w")]<Return>)<Return><Esc>

nmap sp :set paste<Return><Esc>
nmap nsp :set nopaste<Return><Esc>

"" yank
noremap <silent> cy :call system('win32yank.exe -i', @")<CR>
noremap <silent> cp :call setreg('c',system('win32yank.exe -o'))<CR>"cp

set showmatch
set matchtime=1
set matchpairs& matchpairs+=<:>

" Shift + j でイイ感じのスクロール
nnoremap J :call comfortable_motion#flick(100)<CR>
nnoremap K :call comfortable_motion#flick(-100)<CR>
vnoremap J j
vnoremap K k
noremap <silent> cp :call setreg('c',system('win32yank.exe -o'))<CR>"cp:%s/\r//g<CR>

" tigを開く
nnoremap <Leader>t :TigOpenProjectRootDir<CR>

" 現在のファイルの履歴を見る
nnoremap <Leader>T :TigOpenCurrentFile<CR>

" パターンでtig grepする
nnoremap <Leader>g :TigGrep<CR>

" tig grepした内容を再呼び出しする
nnoremap <Leader>r :TigGrepResume<CR>

" 選択中のキーワードでtig grepする
vnoremap <Leader>g y:TigGrep<Space><C-R>"<CR>

" カーソル下のキーワードでtig grepする
nnoremap <Leader>cg :<C-u>:TigGrep<Space><C-R><C-W><CR>

" 現在のカーソル位置でtig blameする
nnoremap <Leader>b :TigBlame<CR>


nmap date i<C-R>=strftime("%Y-%m-%d")<Return> (<C-R>=[ "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" ][strftime("%w")]<Return>)<Esc>
nmap time i<C-R>=strftime("%H:%M:%S")<Return> >> 

```

>>>

ここにプラグインを記述

```
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

Plugin 'VundleVim/Vundle.vim'

" 導入したいプラグインを以下に列挙
" Plugin '[Github Author]/[Github repo]' の形式で記入
"" git
Plugin 'airblade/vim-gitgutter'

"" vue.js
Plugin 'posva/vim-vue'

"" rails
Plugin 'tpope/vim-rails'

"" python
Plugin 'hdima/python-syntax'
Plugin 'heavenshell/vim-pydocstring'

"" html
" Plugin 'alvan/vim-closetag'
Plugin 'valloric/matchtagalways'

"" nerdtree
Plugin 'scrooloose/nerdtree'

"" autocomplete 
Plugin 'valloric/youcompleteme'
" Plugin 'neoclide/coc.nvim'

"" lightline
" Plugi 'itchyny/lightline.vim'
Plugin 'vim-airline/vim-airline'
Plugin 'vim-airline/vim-airline-themes'

"" icons
Plugin 'ryanoasis/vim-devicons'

"" tagbar
Plugin 'majutsushi/tagbar'

"" indentline
Plugin 'yggdroot/indentline'

"" docker 
Plugin 'ekalinin/dockerfile.vim'

"" filer
Plugin 'shougo/unite.vim'
Plugin 'shougo/vimfiler.vim'

"" comment out 
Plugin 'scrooloose/nerdcommenter'
Plugin 'joom/vim-commentary'

"" space + qr -> exec script
Plugin 'thinca/vim-quickrun'

"" linter
" Plugin 'dense-analysis/ale'

Plugin 'deton/jasegment.vim'
Plugin 'yuttie/comfortable-motion.vim'

Plugin 'iberianpig/tig-explorer.vim'

" snippet
Plugin 'sirver/ultisnips'
Plugin 'honza/vim-snippets'
Plugin 'shougo/neosnippet.vim'
Plugin 'shougo/neosnippet-snippets'

call vundle#end()
```

---

よくある操作

```
# 縦分割
ss

# 横分割
sv 

# ﾍﾟｰﾝ移動
s + h j k l

# タブ作成
te

# タブ移動
tab

# ファイラー
fe

# ツリー
ne

# 定義ジャンプ
ta
```

---

# tmuxを使おう

---

tmuxは画面をいろいろできる
<br>
prefixというものと何かを押すことでいろいろ操作

---

`~/.tmux.conf`を作ろう（初期時点ではないはず）

```
# prefixはCtl+f
set-option -g prefix C-f

# vimライクにペインの移動
bind -r k select-pane -U 
bind -r j select-pane -D 
bind -r h select-pane -L 
bind -r l select-pane -R

# Vimのキーバインドでペインをリサイズする
bind -r H resize-pane -L 5
bind -r J resize-pane -D 5
bind -r K resize-pane -U 5
bind -r L resize-pane -R 5

# window移動
bind-key -n C-S-Left swap-window -t -1
bind-key -n C-S-Right swap-window -t +1

# ステータスバーの色を設定する
set -g status-fg black
set -g status-bg yellow

# d でペインを縦に分割する
bind d split-window -hc "#{pane_current_path}"

# D でペインを横に分割する
bind D split-window -vc "#{pane_current_path}"

# new-window (current directory)
bind c new-window -c "#{pane_current_path}"

set -g mouse on
set -g terminal-overrides 'xterm*:smcup@:rmcup@'

bind -r e kill-pane -a

set-window-option -g mode-keys vi

# set-option -g terminal-overrides 'xterm*:colors=256'
# run-shell "powerline-daemon -q"
# source ~/.pyenv/versions/3.7.0/lib/python3.7/site-packages/powerline/bindings/tmux/powerline.conf

# status line を更新する間隔を 1 秒にする
set-option -g status-interval 1

# window-status を中央揃えで配置する
set-option -g status-justify "centre"

# status line の背景色を指定する。
set-option -g status-bg "colour238"

# status line の文字色を指定する。
set-option -g status-fg "colour255"

# status-left の最大の長さを指定する。
set-option -g status-left-length 20

# status-left のフォーマットを指定する。
set-option -g status-left "#[fg=colour255,bg=colour241]Session: #S #[default]"

# status-right の最大の長さを指定する。
set-option -g status-right-length 60

# status-right のフォーマットを指定する。
set-option -g status-right "#[fg=colour255,bg=colour241] #h | LA: #(cut -d' ' -f-3 /proc/loadavg) | %m/%d %H:%M:%S#[default]"

# window-status のフォーマットを指定する。
set-window-option -g window-status-format " #I: #W "

# カレントウィンドウの window-status のフォーマットを指定する
set-window-option -g window-status-current-format "#[fg=colour255,bg=colour27,bold] #I: #W #[default]"

# Enable 256colrs terminal
set -g default-terminal "screen-256color"

set -g @plugin 'tpm_plugins'               
set -g @plugin 'tmux-plugins/tpm'                 
set -g @plugin 'tmux-plugins/tmux-yank'           
set -g @plugin 'tmux-plugins/tmux-open'           
set -g @plugin 'tmux-plugins/tmux-resurrect'   
set -g @plugin 'tmux-plugins/tmux-battery'       
set -g @plugin 'tmux-plugins/tmux-pain-control'

run-shell '~/.tmux/plugins/tpm/tpm'
```

---

よくある操作
```
# ﾍﾟｰﾝ縦割り
prefix + d 

# ﾍﾟｰﾝ横割り
prefix + D 

# ﾍﾟｰﾝ移動
prefix + h j k l ﾍﾟｰﾝ移動

# 新規ウィンドウ作成
prefix + c 

# ウィンドウを次へ移動
prefix + n

# ウィンドウを前へ移動
prefix + p
```
