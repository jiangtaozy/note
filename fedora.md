- dnf proxy

      sudo vim /etc/dnf/dnf.conf
      proxy=http://127.0.0.1:7777
      cd /home/jemo/src/cow
      ./cow

- fedora upgrade

      sudo dnf upgrade --refresh
      sudo dnf install dnf-plugin-system-upgrade
      # Keep eyes on the next line, this should be the version you upgrade too.
      sudo dnf system-upgrade download --releasever=30
      #Reboot
      sudo dnf system-upgrade reboot

- git@gitee.com: Permission denied (publickey).

      vi ~/.ssh/config
      Host gitee.com
      PubkeyAcceptedKeyTypes=+ssh-rsa

- disable "recent files" folder

      gsettings set org.gnome.desktop.privacy remember-recent-files false

- 到铁塔12楼后wifi断掉问题解决：

      重启电脑
