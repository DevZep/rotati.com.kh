# Rotati Website Domain for Cambodia

## Background

In Cambodia its now required to register the domestic TLD that matches your registered company name. In our case, the locally registered business for DevZeo is ROTATI Co. LTD. Therefore we have registered the local domain `rotati.com.kh`.

## Update Content

The site comprises of a simple single page, static site that is hosted in AWS. To update the site simply run: 

**Note you need your ssh public key to be added to the server first.** 

```
scp index.html developer@sobot:~
```

Now ssh into the server and run the following:

```
sudo mv index.html /var/www/rotati.com.kh/.
```

## Config Nginx 

Configuration for Nginx is in `/etc/nginx/sites-available` folder.

## SSL Cert using LetsEncrypt

The sites have SSL certificates using LetsEncrypt. Check [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04) for details. 

To register and install a new SSL cert run the following:

```
sudo certbot --nginx -d rotati.com.kh -d www.rotati.com.kh
```

The certbot is configured to renew every 30 days. Check the settings using:

```
sudo systemctl status certbot.timer
```

## Restart Nginx

You may sometimes need to restart Nginx. To do so, ssh into the server and then run:

```
sudo service nginx restart
```

## Live Site

If everything is working then the site should be securly available via `https` at this location: https://rotati.com.kh and at https://www.rotati.com.kh