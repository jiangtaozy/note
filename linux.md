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
      find ./ -type f -exec sed -i 's/old-text/new-text/g' {} \; // not in fish shell
