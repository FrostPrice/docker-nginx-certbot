# Docker Nginx Certbot

This repository contains a docker-compose for a Nginx server with Certbot (Letsencrypt) with automatic certificate renew.

## How to use

1. Clone this repository
2. In the /data/nginx/proxy.conf, change the my.domain.com to your actual domain
3. In the init-letsencrypt.sh file, replace the following variables with your own values:
   - `domains`: Your domain name
   - `email`: Your email address
   - `staging`: Set to 1 if you're testing your setup to avoid hitting request limits and to 0 when you're ready to issue real certificates
4. Run the init-letsencrypt.sh script
5. Enjoy!

## OBS

- The certificates are validated every 12 hours and the nginx will be reload in every 6 hours.
- You may add as many services you want in the docker-compose file
- For security purpouses, the proxy will always redirect to https
