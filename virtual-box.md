- Install VBoxWindowsAdditions

      Computer -> CD Drive VirtualBox Guest Additions -> VBoxWindowsAdditions

- 开放虚拟机ip

      Settings -> Network -> Attached to: Bridged Adapter

      If the value is Bridged Adapter, do following

      find the ip address of host and guest
      if you are on windows, run ipconfig and get the ip address

          ipconfig

      if you are on Linux, Unix, or Mac OS, run ifconfig | grep 'inet' and get ip address

          ifconfig | grep 'inet'

      the ip address is like 192.168.1.1
      if you want to access host, run browser in guest and enter ip address of host
      if you want to access guest, run browser in host and enter ip address of guest

      控制面板\系统和安全\Windows Defender 防火墙\自定义设置 -> 关闭防火墙

- Install Oracle VM VirtualBox Extension Pack

      sudo VBoxManage extpack install ~/Downloads/Oracle_VM_VirtualBox_Extension_Pack-5.1.38.vbox-extpack

- Installing the VirtualBox Guest Additions

      Devices -> Installing Guest Additions
