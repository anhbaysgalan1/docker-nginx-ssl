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

```