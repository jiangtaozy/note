- 开启防火墙端口

      # 设置开放的端口号
      firewall-cmd --add-service=http --permanent
      firewall-cmd --add-port=3128/tcp --permanent

      # 重启防火墙
      firewall-cmd --reload

      # 查看状态
      systemctl status firewalld

      # 查看所有打开的端口
      firewall-cmd --zone=public --list-ports
