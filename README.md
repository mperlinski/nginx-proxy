# nginx-proxy

## Requirements
- Docker
- Text editor

## Instruction

1. Run this command to start nginx-proxy.<br>
```docker run -d -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock:ro nginxproxy/nginx-proxy```<br>

2. Then create file .env use command<br>
```touch .env```<br>

To check if file exists use command.<br>
```ls -a``` or ```ls -la``` for extra information<br>

3. Edit file with text editor for example vim.<br>
```vim .env```<br>
and add two lines<br>
VIRTUAL_HOST=mydomain.com<br>
COMPOSE_PROJECT_NAME=projectname<br>

4. Then run command which create nginx container with .env file configuration and share volume between host and container.<br>
```docker run -d -p 8080:80 --name nginx --env-file .env -v /etc/nginx/conf.d:/etc/nginx/conf.d -v /etc/nginx/sites-available:/etc/nginx/vhost.d nginx```


