- 扫描局域网IP

      nmap -sn 192.168.0.0/24

- 登录树莓派

      ssh pi@192.168.0.175
      password: raspberry

- 监控温度

      /opt/vc/bin/vcgencmd measure_temp

- 安装工具

      apt install xx

- 安装蓝牙

      sudo systemctl start bluetooth
      sudo systemctl stop bluetooth
      systemctl status bluetooth

      sudo apt install bluetooth pi-bluetooth bluez
      sudo usermod -G bluetooth -a pi
      sudo reboot

      bluetoothctl
      scan on
      scan off
      devices
      pair 54:46:6B:01:55:3A
      connect 54:46:6B:01:55:3A

- 安装busio

      pip3 install Adafruit-Blinka

- 安装adafruit_pca9685

      pip3 install adafruit-circuitpython-pca9685

- 安装adafruit_motor

      pip3 install adafruit-circuitpython-motor
