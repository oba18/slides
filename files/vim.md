# Vi-Improved
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
