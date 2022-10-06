- Aligning table cells, junegunn/vim-easy-align

      gaip*|
      vipga=
        visual-select inner paragraph
        Start EasyAlign command (ga)
        Align around =
      gaip=
        Start EasyAlign command (ga) for inner paragraph
        Align around =

      = Around the 1st occurrences
      2= Around the 2nd occurrences
      *= Around all occurrences
      **= Left/Right alternating alignment around all occurrences
      <Enter> Switching between left/right/center alignment modes


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

- 把一个很长的一行按空格分为多行

      :%s/ +/\r/g
      简单解释一下：
      %s ：在整个文件范围查找替换
      / ：分隔符
      + ：匹配空格，其中“ ”表示空格，+表示重复1次或多次，加在一起表示一个或多个空格。
      /r ：换行符
      /g ：全局替换
      选区，在Visual模式下选择区域后输入:，Vim即可自动补全为 :'<,'>。

- 删除文章中的空行

      :g/^s*$/d
      简单解释一下：
      g ：全区命令
      / ：分隔符
      ^s*$ ：匹配空行，其中^表示行首，s表示空字符，包括空格和制表符，*重复0到n个前面的字符，$表示行尾。连起来就是匹配只有空字符的行，也就是空行。
      /d ：删除该行

- 删除行尾空格：

      :%s= *$==
      :%s/ *$//
      该命令全局查找文本文件的行尾空格并删除。
      解释：
      %s全局查找替换
      =为%s命令的分隔符，如果把=换为/，则该命令可以写为:%s/ *$//
      ” *$”, $表示行尾，*匹配前面0个到n个字符，*前面是空格，因此此正则表达式匹配行尾的0个到n个字符。
      ==，分隔符没有中间没有内容，表示删除匹配空格, 在这里表示删除行尾空格。

- 如何快速去掉^M呢，采取以下步骤就行了：

      1. vi dosfilename
      2. Press Esc
      3. Enter this string: %s/^M//g  (^M = Ctrl v + Ctrl m)
      4. Press enter  (the ^M cleared!)
      5. :wq! (save the file)

- 选区替换`,`为`,回车`

      :'<,'>s/,/,\r/cg

- 小写转大写

      gU

- 大写转小写

      gu

- 行排序

      The following command will sort all lines and remove duplicates (keeping unique lines):
      :sort u

- 统计字符串次数

      :%s/pattern//gn
      % - 指明操作区间，%表示全文本；可以使用1,$或者行区间代替
      s – substitute，表示替换
      pattern - 要查找的字符串
      // - 替代文本应该放在这里，两个斜杠中间没有任何字符表示无替代文本
      g – Replace all occurences in the line. Without this argument, replacement occurs only for the first occurence in each line.
      n – Report the number of matches, and do not actually substitute. 这是核心功能，同时也说明为什么//之间可以添加任意字符。

- 统计字符

      v
      "上下选中所选区域
      g
      Ctrl+g

- 查看vim版本是否支持clipboard

      vim --version | grep "clipboard"

- 隔行合并

      g/^/ join

      上面用到了:gbobal命令，gbobal命令格式如下：

      :[range]global/{pattern}/{command}
      global命令实际上是分成两步执行：首先扫描[range]指定范围内的所有行，给匹配{pattern}的行打上标记；
      然后依次对打有标记的行执行{command}命令，如果被标记的行在对之前匹配行的命令操作中被删除、移动或合并，则其标记自动消失，而不对该行执行{command}命令。
      {command}可以是一个ex命令，也可以是用|分隔的多个ex命令，这样我们就可以对被标记行，或从标记行寻址到的行进行多种不同的操作。

      shift + v 选中 ：g/^/ join

- 查找替换为大写字母
      %s/_./\U&/g
      aaa_Bbb

      :'<,'>s/_./\U&/g

      %s/abc/\U&/g
      替换“abc xxxxabcxxxxx abc”为“ABC xxxxABCxxxxx ABC”

      %s/{.*}/\L&/g
      替换“{ABC} xxxx{DEF}xxxxx {ABC}”为“{abc} xxxx{def}xxxxx {abc}”

      \L 是小写；
      \U 是大写；
      &是正则表达式全部匹配项，
      其他的还有：\1,\2,\3,…,\9。表示第1，2，3…9个匹配项。

- 删除空格行

      :g/^$/d

- 删除行首空格

      :%s/^\s*//g
      :'<,'>s/^\s*//g

- 删除行尾空格

      :%s/\s*$//g

- 排序和去重

      :sort u
