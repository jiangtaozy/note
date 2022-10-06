- 默认前导键
      ctrl + b
- 切换窗口
      Ctrl+b ;：光标切换到上一个窗格。
      Ctrl+b o：光标切换到下一个窗格。
- tmux new -s session # 建立会话
- tmux kill-session -t demo # 关闭demo会话
- ctrl + a c # 新建窗口
- ctrl + a 0-9 # 切换窗口
- ctrl + a " # 水平分屏
- ctrl + a % # 垂直分屏

- tmux: error while loading shared libraries: libevent-2.1.so.7: cannot open shared object file: No such file or directory

      ln -s /usr/local/lib/libevent-2.1.so.7 /usr/lib64/libevent-2.1.so.7

- scroll around.

      Ctrl-b then [
      Press q to quit scroll mode.
