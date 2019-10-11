- Copy ssh id_rsa.pub to remote server

      ssh-copy-id user@hostname.example.com

- Generating a new SSH key

      ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
