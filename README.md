# ansible-nginx

A quick Ansible role to configure nginx, virtual hosts, and (optionally) Let's Encrypt certificates with webhook validation.

I also attempt to keep this role up to date with [Mozilla's SSL Config Generator](https://ssl-config.mozilla.org/#server=nginx&config=intermediate&hsts=false&ocsp=false) (see `snippets/nginx-ssl.conf.j2`)

## Variables

```yaml
# Site to configure. src is the source template file of an nginx `server{}` directive (usually from the current role), dst is the name to upload it as under /etc/nginx/sites-available
nginx_site:
  src: srcfile.conf.j2
  dst: srcfile.conf

# If non-empty, attempts to create an SSL certificate for the given domains using certbot's webroot validation
letsencrypt_domains: []

# webroot path for certbot validation
letsencrypt_webroot_path: /var/www/html
letsencrypt_account_email: your@email
```
