# Nginx
## Hide version number
- Recompile from source and change version number
```nginx
server_tokens off;
server_name_in_redirect off;
port_in_redirect off;
```
## HTTPS redirect
```nginx
server {
	listen 80;
	server_name *.domain.com;
	return 301 https://$host$request_uri;
}
server {
	listen 443 ssl;
	listen [::]:443 ssl;
	server_name *.domain.com;
}
```
## HTTP/2
```nginx
listen 443 ssl http2;
listen [::]:443 ssl http2;
```
## TLS 1.3
```nginx
ssl_protocols TSLv1.3;
```
### Ciphers
### Early data
```nginx
ssl_early_data on;
```
In proxy directive:
```nginx
proxy_set_header Early-Data $ssl_early_data;
```
## Compression
