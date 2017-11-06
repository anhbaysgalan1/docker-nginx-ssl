# Docker container - NGINX with SSL

## Create the ssl certificates (Ignore if you have ssl of your own)

We can start off by creating a directory that will be used to hold all of our SSL information.

```bash
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout nginx.key -out nginx.crt
```

## Create a local host 

*NOTE : Ignore if you have public domain poit it to server IP where you run nginx*

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

If you are able to access your app from http://123.12.1.4:8080/, then this property looks something like this

```txt
proxy_pass http://123.12.1.4:8080/;
```

2. Copy your ssl files and Rename the .crt, .key files based on your file names

```txt
Either rename nginx.key , nginx.crt files in ssl folder 

OR

in *nginx.conf* rename the value of the properties ssl_certificate, ssl_certificate_key
```

If you find any issues please raise and issue on issues tab
