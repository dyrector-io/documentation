# Proxies

Proxies provide secure connection when you set up the platform for self-managed use. But they can be useful for any other uses, when you need a firewall, or you'd like to hide your location, and so on.

**When you set up the platform, we highly recommend you to use a proxy, such as Traefik or NGINX, to secure your network.**

### Traefik

Traefik is used by default, as seen in the [**docker-compose**](https://github.com/dyrector-io/dyrectorio/blob/develop/docker-compose.yaml) designed for production use.

### NGINX

By default we recommend using Traefik but if you already use NGINX then here's an example.

When you configure NGINX for the platform, keep in mind the following:

Inbound traffic needs to be directed towards 3 containers: kratos, crux-ui, and crux. The 5 locations defined are below:

* /crux-ui
* /kratos (needs to be stripped)
* Locations routed to crux-ui:
  * /api/auth
  * /api/status
  * /api

#### Example NGINX config with default ports:

```nginx
upstream crux-ui {
    server localhost:3000;
}

upstream crux {
    server localhost:1848;
}

upstream kratos {
    server localhost:4433;
}

server {
    listen 80;
    listen [::]:80;

    server_name example.com;

    client_max_body_size 128m;

    proxy_read_timeout 300;
    return 301 https://$host$request_uri;
}

server {
    listen 443 ssl http2;
    listen [::]:443 ssl http2;

    server_name example.com;

    ssl_certificate /etc/ssl/ssl.crt;
    ssl_certificate_key /etc/ssl/ssl.key;

    client_max_body_size 128m;

    proxy_set_header Host $http_host; # required for docker client's sake
    proxy_set_header X-Real-IP $remote_addr; # pass on real client's IP
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_read_timeout 900;

    location / {
        proxy_pass http://crux-ui;
    }

    location /kratos {
        rewrite ^/kratos(.*)$ /$1 break;

        proxy_pass http://kratos;
    }

    location /api/auth {
            proxy_pass http://crux-ui;
    }
    
    location /api/status {
            proxy_pass http://crux-ui;
    }

    location /api {
                proxy_pass http://crux;
    }
}
```
