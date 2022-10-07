- Download file with curl

      curl -O https://www.w3schools.com/html/mov_bbb.mp4
      curl -o newfile.tar.gz http://yourdomain.com/yourfile.tar.gz

- Curl output json format

      curl "http://127.0.0.1:4000/assets/site-mgt/site?page=2&pageSize=2" | json_pp

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

- List the TCP ports that are being listened on 查看端口

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

      Install Mono
      mono Fiddler.exe
      [Tools] –> [Fiddler Options] -> [Connections] ，端口 8888， 勾选 Allow remote computers to connect，重启 Fiddler
      手机设置代理 修改网络->显示高级选项->代理->手动，主机 电脑局域网 IP，端口 8888
      fiddler 命令行中输入: bpafter http://hashuo.chslab.com
      手机访问 http://hashuo.chslab.com, 插入 <script src="http://192.168.31.217:9090/target/target-script-min.js#anonymous"></script>

- Screenshot

      gnome-screenshot --interactive

- Shortcut to close terminal

      <kbd>ctrl</kbd>+<kbd>D</kbd>

- Copy ssh id_rsa.pub to remote server

      ssh-copy-id user@hostname.example.com

- Extract a zip file to a specific folder

      unzip /path/to/file.zip -d temp_for_zip_extract

- Zip directory

      zip –r filename.zip directory_name

- How to syntax highlight via Less

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

- Display available WiFi networks

      nmcli dev wifi:

- Connect to a wireless AP:

      nmcli dev wifi connect lz_chslab_netgear password 123456@lz

- Disconnect wifi

      nmcli dev disconnect wlo1

- Find last system reboot time/date

      who -b
      last reboot | less
      last reboot | head -1

- Finding systems last shutdown date and time

      last -x | grep shutdown | head -1

- Find out Linux system up since…

      uptime -s

- ls sort the files according to the time stamp

      ls -lt

- Create tar Archive File

      tar -cvf tecmint-14-09-12.tar /home/tecmint

- 解压 Extract a .tar file

      tar -xvf file.tar
      tar -xzvf file.tar.gz
      tar -xzvf file.tgz
      tar -xjvf file.tar.bz2
      tar -xvf file.tar.xz

- Extract a .gz file

      gunzip file.gz

- Systemd Fedora startup script permission denied

      in /etc/selinux/config
      set the line
      SELINUX = enforcing
      to
      SELINUX = permissive

- Systemd service

      /usr/lib/systemd/system/shadowsocks.service

      [Unit]
      Description=shadowsocks

      [Service]
      Type=forking
      ExecStart=/home/jemo/src/shadowsocks/shadowsocks-local-linux64-1.1.5

      [Install]
      WantedBy=multi-user.target

      sudo systemctl enable shadowsocks.service
      sudo systemctl disable shadowsocks.service

- Fedora enable pinyin

      ibus-daemon &
      ibus engine libpinyin

- Extract a rar file

      unrar x tecmint.rar

- Run mov video file

      sudo apt-get install libopus0
      sudo apt-get install gstreamer1.0-libav

- Install RPM File

      rpm -ivh awstats.i386.rpm

- Check the battery's status via the terminal

      upower -e
      upower -i /org/freedesktop/UPower/devices/DisplayDevice

- To set the master volume

      amixer scontrols
      amixer sset 'Master' 50%

- Check disk space usage

      df -hl

- Get total disk usage size of an directory

      du -sh dir
      du -sh *

- Remove all node_modules

      find ./ -depth -name "node_modules" -type d -exec rm -rf "{}" \;

- View chm file

      kchmviewer

- Make symbolic links

      ln -s target link-name

- Open libreoffice

      libreoffice

- Recursive mkdir

      mkdir -p foo/bar/zoo/andsoforth

- Information about the Linux distribution and version

      cat /etc/*release*

- Get the Linux Kernel Version

      uname -v

- Check battery status

      cat /sys/class/power_supply/BAT0/capacity

- Check RAM

      free

- Check file number

      ls | wc -w

- Merging folders with mv

      rsync -av /source /destination

- Arandr xrandr gui

      arandr

- QQ file path

      手机存储/Android/data/com.tencent.mobileqq/Tencent/QQfile_recv

- Update virtualbox

      rpm -qa | grep -i virtualbox
      sudo dnf remove VirtualBox-6.0-6.0.4_128413_fedora29-1.x86_64
      sudo dnf remove virtualbox-guest-additions-6.0.4-2.fc29.x86_64

      sudo dnf install VirtualBox-6.1-6.1.14_140239_fedora29-1.x86_64.rpm
      sudo virtual
      install Oracle_VM_VirtualBox_Extension_Pack-6.1.14.vbox-extpack

- 同屏传输

      obs
      ./objs/srs -c conf/rtmp.conf
      FMS URL: rtmp://192.168.1.170/live
      Stream: livestream
      http://ossrs.net/srs.release/trunk/research/players/srs_player.html?app=live&stream=livestream&server=192.168.0.147&port=1935&autostart=true&vhost=192.168.0.147

- 压缩图片/裁剪图片

      convert -resize 800x800 5.png 5-1.png

      # resize an image to a width of 200
      convert example.png -resize 200 example.png

      # resize an image to a height of 100
      convert example.png -resize x100 example.png

      #批量裁剪/压缩
      #resizes all of the .png files in your directory to a size of 960 pixels by 528 pixels.
      mogrify -resize 960x528 *.png

      #scale all of your images to a width of 960 pixels, the height will be scaled accordingly, preserving the aspect ratio.
      mogrify -resize 960 *.png

      mogrify -resize 1500 *.jpg

- 当前目录下所有gif文件转化为jpg文件

      mogrify -format jpg *.gif

- 连接局域网打印机

      sudo dnf install cups
      service cups start
      http://localhost:631
      Add Printer-Discovered Network Printers

- 扫描局域网IP

      nmap -sn 192.168.0.0/24

- 删除已连接WIFI

      nmcli con show
      nmcli con delete UUID

- 创建热点

      ip link show
      nmcli con add type wifi ifname wlo1 con-name ap autoconnect yes ssid ap
      nmcli con modify ap 802-11-wireless.mode ap 802-11-wireless.band bg ipv4.method shared
      nmcli con up ap
      nmcli con down ap // 关闭热点
      nmcli con delete ap // 删除热点

- scp 下载文件

      scp -P 2222 root@www.vpser.net:/root/lnmp0.4.tar.gz /home/lnmp0.4.tar.gz
      上端口大写P 为参数，2222 表示更改SSH端口后的端口，如果没有更改SSH端口可以不用添加该参数。 root@www.vpser.net 表示使用root用户登录远程服务器www.vpser.net，:/root/lnmp0.4.tar.gz 表示远程服务器上的文件，最后面的/home/lnmp0.4.tar.gz表示保存在本地上的路径和文件名。

- scp 上传文件
      scp -P 2222 /home/lnmp0.4.tar.gz root@www.vpser.net:/root/lnmp0.4.tar.gz
上端口大写P 为参数，2222 表示更改SSH端口后的端口，如果没有更改SSH端口可以不用添加该参数。 /home/lnmp0.4.tar.gz表示本地上准备上传文件的路径和文件名。root@www.vpser.net 表示使用root用户登录远程服务器www.vpser.net，:/root/lnmp0.4.tar.gz 表示保存在远程服务器上目录和文件名。

- 解压文件内容乱码问题

      iconv -f gbk -t utf8 报帐系统部署说明.txt > 报帐系统部署说明.txt.utf8

- 解压文件目录文件名乱码问题

      convmv -f GBK -t utf8 -r --notest \Xd5㽭ʡ/

- 修改文件权限

      chmod u/g/o/a +/-/= rwx 文件

- 视频剪辑

      shotcut

- crontab Linux 定时执行shell 脚本

      crontab –e     //修改 crontab 文件，如果文件不存在会自动创建。
      crontab –l      //显示 crontab 文件。
      crontab -r      //删除 crontab 文件。
      crontab -ir     //删除 crontab 文件前提醒用户。

      service crond status     //查看crontab服务状态
      service crond start     //启动服务
      service crond stop     //关闭服务
      service crond restart     //重启服务
      service crond reload     //重新载入配置

      *　　*　　*　　*　　*　　command
      分   时　 日　 月　 周　  命令

      每天凌晨00:10运行
      10 0 * * * sh test.sh
      每天10点运行
      0 10 * * * /root/tool/node-v10.16.0-linux-x64/bin/node /root/project/data-cleaning/day-clean-switch.js


      执行日志：/var/log/cron
      结果日志：/var/spool/mail/root

      发送错误邮件：
      crontab -e
      最上面添加
      MAILTO=email@example.com

- crontab /bin/sh: node: command not found

      cron use do not configure the PATH in the same way as your user, and do not know node nor npm.
      you can use the absolute path in your crontab:

      0 * * * * /some/path/to/node /path/to/your/script.js

- linux 离线安装gcc

      1. 从CentOS7的系统安装镜像中取出需要的rpm包:
      http://mirrors.aliyun.com/centos/7/os/x86_64/Packages/
      mpfr-3.1.1-4.el7.x86_64.rpm
      libmpc-1.0.1-3.el7.x86_64.rpm
      kernel-headers-3.10.0-123.el7.x86_64.rpm
      glibc-headers-2.17-55.el7.x86_64.rpm
      glibc-devel-2.17-55.el7.x86_64.rpm
      cpp-4.8.2-16.el7.x86_64.rpm
      gcc-4.8.2-16.el7.x86_64.rpm

      2. 将这些包上传到待安装的系统中使用如下命令统一安装：
      rpm -Uvh *.rpm --nodeps --force

- source

      source FILENAME [arguments]

- linux 离线安装pip


      1. 安装libffi libffi-devel
      http://mirrors.aliyun.com/centos/7/os/x86_64/Packages/
      libffi-3.0.13-19.el7.x86_64.rpm
      libffi-devel-3.0.13-19.el7.x86_64.rpm
      2. 安装zlib zlib-devel
      zlib-1.2.7-18.el7.x86_64.rpm
      zlib-devel-1.2.7-18.el7.x86_64.rpm
      rpm -Uvh *.rpm --nodeps --force
      3. 安装setuptools
      https://pypi.python.org/pypi/setuptools
      python3 setup.py install
      4. 安装pip
      https://pypi.python.org/pypi/pip
      python3 setup.py install

- linux 离线安装 python pip 包

      pip install /home/user/package/tqdm-4.28.1-py2.py3-none-any.whl

- CentOS7 离线安装gcc/pcre-devel/openssl-devel/zlib-devel


      1. 下载以下rpm
      http://mirrors.aliyun.com/centos/7/os/x86_64/Packages/
      autogen-libopts-5.18-5.el7.x86_64.rpm
      cpp-4.8.2-16.el7.x86_64.rpm
      gcc-4.8.2-16.el7.x86_64.rpm
      glibc-devel-2.17-55.el7.x86_64.rpm
      glibc-headers-2.17-55.el7.x86_64.rpm
      kernel-headers-3.10.0-123.el7.x86_64.rpm
      keyutils-libs-devel-1.5.8-3.el7.x86_64.rpm
      krb5-devel-1.11.3-49.el7.x86_64.rpm
      libcom_err-devel-1.42.9-4.el7.x86_64.rpm
      libmpc-1.0.1-3.el7.x86_64.rpm
      libselinux-devel-2.2.2-6.el7.x86_64.rpm
      libsepol-devel-2.1.9-3.el7.x86_64.rpm
      libverto-devel-0.2.5-4.el7.x86_64.rpm
      mpfr-3.1.1-4.el7.x86_64.rpm
      ntp-4.2.6p5-18.el7.centos.x86_64.rpm
      ntpdate-4.2.6p5-18.el7.centos.x86_64.rpm
      openssl098e-0.9.8e-29.el7.centos.x86_64.rpm
      openssl-1.0.1e-34.el7.x86_64.rpm
      openssl-devel-1.0.1e-34.el7.x86_64.rpm
      openssl-libs-1.0.1e-34.el7.x86_64.rpm
      pcre-devel-8.32-12.el7.x86_64.rpm
      pkgconfig-0.27.1-4.el7.x86_64.rpm
      tcl-8.5.13-4.el7.x86_64.rpm
      zlib-1.2.7-13.el7.x86_64.rpm
      zlib-devel-1.2.7-13.el7.x86_64.rpm

      2. 安装
      rpm -Uvh ./*.rpm --nodeps --force

- centos7 防火墙开启端口

      firewall-cmd --zone=public --add-port=30030/tcp --permanent
      firewall-cmd --reload
      firewall-cmd --zone=public --list-ports

- 修改用户

      把文件yusi123.com的所有者改为yusi。
      chown yusi yusi123.com
      把目录/demo及其下的所有文件和子目录的属主改成yusi，属组改成users。
      chown - R yusi.users /demo

- shell 标出输入、标准输出、错误输出

      shell中可能经常能看到：>/dev/null  2>&1
      eg：sudo kill -9 `ps -elf |grep -v grep|grep $1|awk '{print $4}'` 1>/dev/null 2>/dev/null

      命令的结果可以通过%>的形式来定义输出

      /dev/null 代表空设备文件
      > 代表重定向到哪里，例如：echo "123" > /home/123.txt
      1 表示stdout标准输出，系统默认值是1，所以">/dev/null"等同于"1>/dev/null"
      2 表示stderr标准错误
      & 表示等同于的意思，2>&1，表示2的输出重定向等同于1

      那么本文标题的语句：
      1>/dev/null 首先表示标准输出重定向到空设备文件，也就是不输出任何信息到终端，说白了就是不显示任何信息。
      2>&1 接着，标准错误输出重定向等同于 标准输出，因为之前标准输出已经重定向到了空设备文件，所以标准错误输出也重定向到空设备文件。

- centos7 配置代理

      #代理服务器
      yum install -y squid
      vi /etc/squid/squid.conf
      #将http_access deny all注释修改为http_access allow all
      #http_access deny all
      http_access allow all
      service squid start
      netstat -an | grep 3128
      #开启防火墙端口
      firewall-cmd --zone=public --add-port=3128/tcp --permanent
      firewall-cmd --reload
      firewall-cmd --zone=public --list-ports

      #代理客户端
      vi .bashrc
      export http_proxy=http://172.17.13.102:3128
      export https_proxy=http://172.17.13.102:3128
      source .bashrc

      curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo

      #报错http://mirrors.aliyun.com/centos/6Server/os/x86_64/repodata/repomd.xml: [Errno 14] PYCURL ERROR 22 - "The requested URL returned error: 404 Not Found"
      这是因为我这个虚拟机用的centos6的镜像，但是这个版本已经找不到了，我们替换为7就可以
      修改CentOS-Base.repo文件
      vi /etc/yum.repos.d/CentOS-Base.repo
      使用全局替换命令，将该文件中$releasever全部改成7
      :%s/$releasever/7/g

      #ssh代理
      vi ~/.ssh/config
      Host *
        ProxyJump 172.17.13.102:3128
      chmod 600 ~/.ssh/config

      #关闭squid
      squid -k shutdown
      firewall-cmd --zone=public --remove-port=3128/tcp --permanent
      firewall-cmd --reload
      firewall-cmd --zone=public --list-ports

- centos 7 阿里源

      mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
      curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
      yum makecache

- unzip 中文乱码解决

      ~/Downloads> unzip -O GBK *.zip

- 压缩

      tar -cvf build.tar build


      scp -P 2222 root@www.vpser.net:/root/lnmp0.4.tar.gz /home/lnmp0.4.tar.gz

- 查看端口

      netstat -tunlp

- 查看防火墙状态

      firewall-cmd --state

- 查看防火墙端口

      firewall-cmd --zone=public --list-ports

- 调整屏幕亮度

      xrandr
      xrandr --output eDP --brightness 0.7
      #查看亮度
      xrandr --verbose
      #自动调节
      .bashrc

- gbk 文件名乱码

      convmv -f gbk -t utf-8 -r --notest /home/wwwroot

- gbk 文件内容乱码

      iconv -f gbk -t utf8 tmp.txt > tmp.txt.utf8 -c

- 同步代码

      scp -rp user@ip:/path /path
