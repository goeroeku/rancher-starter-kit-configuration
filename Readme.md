# Sample nginx, php-fpm configuration for Rancher

### Steps

1. Clone this repository

```text
git clone git@github.com:goeroeku/rancher-starter-kit-configuration.git
```

2. Create NGINX Service, add 3 VOLUME, add link to php service, use `image: nginx:alpine`

```text
  volumes:
  - {full directory}/web:/var/www/html
  - {full directory}/conf/nginx.conf:/etc/nginx/nginx.conf
  - {full directory}/conf/default.conf:/etc/nginx/conf.d/default.conf
```

3. Create PHP Service, add 2 VOLUME, add link to database service, use `image: goeroeku/php-fpm-alpine:7.3.1`

```text
- {full directory}/web:/var/www/html
- {full directory}/conf/upload.ini:/usr/local/etc/php/conf.d/uploads.ini
```

4. Put web project on web directory
5. Run Service
6. Open browser and open the ip address given by nginx service
