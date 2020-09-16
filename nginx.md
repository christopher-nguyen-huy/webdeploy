# Nginx
## Hide version number
- Recompile from source and change version number
```nginx
server_tokens off;
server_name_in_redirect off;
port_in_redirect off;
```