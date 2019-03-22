- Let's Encrypt

      wget https://dl.eff.org/certbot-auto
      chmod a+x certbot-auto
      sudo /path/to/certbot-auto certonly --standalone -d example.com -d www.example.com
      Congratulations! Your certificate and chain have been saved at:
      /etc/letsencrypt/live/destpact.com/fullchain.pem
      Your key file has been saved at:
      /etc/letsencrypt/live/destpact.com/privkey.pem
      Your cert will expire on 2019-06-10. To obtain a new or tweaked
      version of this certificate in the future, simply run certbot-auto
      again. To non-interactively renew *all* of your certificates, run
      "certbot-auto renew"

- Create a self-signed certificate with openssl

      openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes
