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

## Restart Nginx

You may sometimes need to restart Nginx. To do so, ssh into the server and then run:

```
sudo service nginx restart
```