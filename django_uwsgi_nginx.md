# Set Django to production with uWSGI and nginx

Setup uwsgi.ini file like:

```
[uwsgi]

plugin = python3
chdir           = /path/to/app/
module          = app.wsgi:application
home            = /path/to/env/

master          = true
# worker processes
processes       = 10
http            = 127.0.0.1:8080 #%(chdir)pdfconvert.sock
# chmod-socket  = 664
vacuum          = true

```

## Nginx config:

Put it in ``/etc/nginx/site-enabled/``


```
server {
	listen 80;
	listen [::]:80;
  #server_name [preurl.]your_server.com
	
  location / {
		proxy_set_header   X-Real-IP $remote_addr;
	  proxy_set_header   Host      $http_host;
		proxy_pass         http://127.0.0.1:8080;
		#include         uwsgi_params;
		#proxy_pass      http://unix:/home/ubuntu/pdfconvert/pdfconvert/pdfconvert.sock;
	}
}

```

restart nginx with `` sudo /etc/init.d/nginx restart``
