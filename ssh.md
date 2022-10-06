- Copy ssh id_rsa.pub to remote server

      ssh-copy-id user@hostname.example.com
      ssh-copy-id root@121.42.24.117

- Generating a new SSH key

      #rsa已被弃用，不再支持
      ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

      ssh-keygen -t ed25519 -C "your_email@example.com"
