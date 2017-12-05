# Nginx https

https://coderwall.com/p/e7gzbq/https-with-certbot-for-nginx-on-amazon-linux


## To redirect all http requests to https


server {
      listen      80 default;
      server_name www.yourdomain.biz yourdomain.biz;
      return      301 https://$server_name$request_uri;
}
