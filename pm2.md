- install pm2

      npm install pm2@latest -g

- Start an app

      pm2 start app.js
      # Specify an app name
      --name <app_name>


- Managing processes

      pm2 restart app_name
      pm2 reload app_name
      pm2 stop app_name
      pm2 delete app_name


- List the status

      pm2 ls

- Display logs

      pm2 logs
      pm2 logs --lines 200

- Terminal Based Dashboard

      pm2 monit

- start

      pm2 start app.js --name <app_name>
