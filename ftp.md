- locat_root:

      /home/mujixing

- restart:

      service vsftpd restart

- connect ftp:

      ftp 121.42.24.17

- download:

      ftp > get /usr/your/xxx.html
      ftp > cd /usr/your/
      ftp > mget *.* (批量下载)

- upload:

      ftp > put xxx.html /usr/your/ (当前目录下的xxx.html)
      ftp > cd /usr/your/
      ftp > mput *.html (批量上传)

- disconnect:

      ftp > bye
