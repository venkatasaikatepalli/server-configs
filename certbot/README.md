# Letsencrypt
 
Install letsencrypt

## Apache2
```
$ sudo apt-get update
$ sudo add-apt-repository ppa:certbot/certbot
$ sudo apt install python-certbot-apache
```

Add ssl file
```
$ sudo nano /etc/apache2/sites-available/example.com.conf

...
ServerName example.com;
...
```

Test and Reload
```
$ sudo apache2ctl configtest
$ sudo systemctl reload apache2
```
Obtaining an SSL Certificate

```
$ sudo certbot --apache -d example.com -d www.example.com

...
Please choose whether or not to redirect HTTP traffic to HTTPS, removing HTTP access.
-------------------------------------------------------------------------------
1: No redirect - Make no further changes to the webserver configuration.
2: Redirect - Make all requests redirect to secure HTTPS access. Choose this for
new sites, or if you're confident your site works on HTTPS. You can undo this
change by editing your web server's configuration.
-------------------------------------------------------------------------------
Select the appropriate number [1-2] then [enter] (press 'c' to cancel):
...
click Enter
```

Verifying Certbot Auto-Renewal
```
$ sudo certbot renew --dry-run
```

Reference Link: [click here](https://www.digitalocean.com/community/tutorials/how-to-secure-apache-with-let-s-encrypt-on-ubuntu-18-04)


## Nginx
```
$ sudo apt-get update
$ sudo add-apt-repository ppa:certbot/certbot
$ sudo apt-get update
$ sudo apt-get install python-certbot-nginx
```

Confirming Nginx's Configuration
```
$ sudo nano /etc/nginx/sites-available/example.com

. . .
server_name example.com www.example.com;
. . .
```

Test and Reload
```
$ sudo nginx -t
$ sudo systemctl reload nginx
$ sudo ufw status
```
Obtaining an SSL Certificate

```
$ sudo certbot --apache -d example.com -d www.example.com

...
Please choose whether or not to redirect HTTP traffic to HTTPS, removing HTTP access.
-------------------------------------------------------------------------------
1: No redirect - Make no further changes to the webserver configuration.
2: Redirect - Make all requests redirect to secure HTTPS access. Choose this for
new sites, or if you're confident your site works on HTTPS. You can undo this
change by editing your web server's configuration.
-------------------------------------------------------------------------------
Select the appropriate number [1-2] then [enter] (press 'c' to cancel):
...
click Enter
```

Verifying Certbot Auto-Renewal
```
$ sudo certbot renew --dry-run
```

Reference Link: [click here](https://www.digitalocean.com/community/tutorials/how-to-secure-apache-with-let-s-encrypt-on-ubuntu-18-04)