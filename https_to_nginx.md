# Nginx https

Blog posts:

1. [Codewall](https://coderwall.com/p/e7gzbq/https-with-certbot-for-nginx-on-amazon-linux)
2. [DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-16-04)


## To redirect all http requests to https

```
server {
      listen      80 default;
      server_name www.yourdomain.biz yourdomain.biz;
      return      301 https://$server_name$request_uri;
}
```
