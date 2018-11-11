- Download file with curl

      curl -O https://www.w3schools.com/html/mov_bbb.mp4

- define an alias in fish shell

      vi ~/.config/fish/config.fish
      alias postman="~/src/Postman/Postman"

- Install autojump on ubuntu

      sudo apt-get install autojump
      vi ~/.bashrc
      . /usr/share/autojump/autojump.sh
      mkdir ~/.config/fish/functions
      cp /usr/share/autojump/autojump.fish ~/.config/fish/functions
      autojump
      j dir-name

- List the TCP ports that are being listened on

      netstat -plnt 

- Find and replace text within a file or directory using sed command

      sed -i 's/old-text/new-text/g' input.txt
      find ./ -type f -exec sed -i 's/old-text/new-text/g' {} \; // not work in fish shell

- open image or other file

      open filename

- android sdk

      tar -xvf android-sdk_r24.2-linux.tgz
      cd android-sdk-linux/tools

- install all sdk packages

      ./android update sdk --no-ui
      export ANDROID_HOME=$HOME/src/android-sdk-linux
      export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools

- Applications not resizing with WM, menus immediately closing

      export _JAVA_AWT_WM_NONREPARENTING=1

- webstorm  auto format code

      Ctrl + Alt + L

- configure a service to run at startup

      1. Open /etc/rc.local file with this command:
          vim /etc/rc.local
      2. Add your script that you want to run on boot process there, for example:
          // start proxy service
          /home/jemo/src/proxy/shadowsocks/shadowsocks-local-linux64-1.1.5
      3. Review the comments included in that file and make sure an exit 0 is at the end.
      4. Save the files. And your script will run on boot process.

- Run bash script / run a service after login

      edit ~/.profile
      /home/jemo/cow &

- Log in failure

      ctrl-alt-F1

- ubuntu uninstall golang-go and its dependencies

      sudo apt-get remove --auto-remove golang-go

- Weinre

      npm -g install weinre
      weinre --boundHost 192.168.31.217 --httpPort 9090
      // Then inside your target document add:
      <script src="http://192.168.31.217:9090/target/target-script-min.js#anonymous"></script>
      // use Chrome open http://192.168.31.217:9090

- Fiddle

  ```
  Install Mono
  mono Fiddler.exe
  [Tools] –> [Fiddler Options] -> [Connections] ，端口 8888， 勾选 Allow remote computers to connect，重启 Fiddler
  手机设置代理 修改网络->显示高级选项->代理->手动，主机 电脑局域网 IP，端口 8888
  fiddler 命令行中输入: bpafter http://hashuo.chslab.com
  手机访问 http://hashuo.chslab.com, 插入 <script src="http://192.168.31.217:9090/target/target-script-min.js#anonymous"></script>
  
  ```

- Screenshot

  ```
  gnome-screenshot --interactive
  ```

- Shortcut to close terminal

  ```
  <kbd>ctrl</kbd>+<kbd>D</kbd>
  ```

- Copy ssh id_rsa.pub to remote server

  ```
  ssh-copy-id user@hostname.example.com
  ```

- Extract a zip file to a specific folder

  ```
  unzip /path/to/file.zip -d temp_for_zip_extract
  ```

- How to syntax highlight via Less

  ```
  # vi .bashrc
  export LESSOPEN="| /usr/bin/src-hilite-lesspipe.sh %s"
  export LESS=' -R '

  As of Debian Stretch and Fedora 25, package names and script paths differ. 

  # Debian
  sudo apt install libsource-highlight-common source-highlight
  dpkg -L libsource-highlight-common | grep lesspipe
  # /usr/share/source-highlight/src-hilite-lesspipe.sh

  # Fedora
  sudo dnf install source-highlight
  rpm -ql source-highlight | grep lesspipe
  # /usr/bin/source-highlight/src-hilite-lesspipe.sh
  ```
