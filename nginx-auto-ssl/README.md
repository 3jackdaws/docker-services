# Nginx Auto SSL
This set of containers sets up an NGINX proxy and companion container.  Both of these containers respond to events on the local Docker socket.

# Nginx
Listens for container events, requires volume binds to the host Docker socket.  Performs the following actions in response to ENV variables in Starting Docker containers:

| Key | Value | Effect |
| --- | ----- | ------ |
| VIRTUAL_HOST | Comma separated FQDNs (test.example.com, example.com, etc.) | Redirects HTTP and HTTPS traffic to the container based on requested domain or subdomain |
| VIRTUAL_PORT | HTTP Port (8080, 1234, etc.) | Specify a different port for the VIRTUAL_HOST proxying, default is 80 |

[Additional Information](https://github.com/jwilder/nginx-proxy)


# Letsencrypt Companion
Listens for container events, requires volume binds to the host Docker socket.  Performs the following actions in response to ENV variables in Starting Docker containers: 

| Key | Value | Effect |
| --- | ----- | ------ |
| LETSENCRYPT_HOST | Comma separated FQDNs (test.example.com, example.com, etc.) | fetches a Letsencrypt cert for the domain or subdomain |
| LETSENCRYPT_EMAIL | email address (test@example.com) | Required to make this work |

[Additional Information](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion)