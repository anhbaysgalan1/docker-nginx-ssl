# Docker container - NGINX with SSL

## Create the ssl certificates

We can start off by creating a directory that will be used to hold all of our SSL information.

```bash
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout nginx.key -out nginx.crt
```

## Create a local host if you have public domain use it

```bash
sudo echo "127.0.0.1 local.jinna.com" >> /etc/hosts
```

## Clone

```bash
    git clone https://github.com/JinnaBalu/docker-nginx-ssl.git
```

## Help

*nginx.conf*

1. Change the below property where you want to redirect to

```txt
proxy_pass https://github.com/JinnaBalu;
```

2. Rename the .crt, .key files based on your file names

```txt
Either rename nginx.key , nginx.crt files in ssl folder 

OR

in *nginx.conf* rename the value of the properties ssl_certificate, ssl_certificate_key
```