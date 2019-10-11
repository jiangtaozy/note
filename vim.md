- Aligning table cells, junegunn/vim-easy-align

      gaip*|

- Comment out the current line or text selected in visual mode. scrooloose/nerdcommenter

      ,cc

- Uncomments the selected line(s)

      ,cu

- Copy word without trailing white space

      ye

- Format code

      select and tap '='

- Join lines without producing a space?

      gJ

- Search current word

      *

- Clear last search highlighting

      :noh

- Text template

      " .vimrc
      :imap <buffer> ;c console.log(": ", );<ESC>
      :imap <buffer> ;l loggger.info(": ", );<ESC>
      " type ;c in insert mode

- Fedora vim access clipboard

      sudo dnf install vim-X11
      // .config/fish/config.fish
      alias vi=vimx

- Syntax highlight for vue.js

      .vimrc
      Plug 'posva/vim-vue'
      :PlugInstall

- Replace from line 5 to line 12

      :5,12s/foo/bar/g

- Count

      :%s/pattern//ng
