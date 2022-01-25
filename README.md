A simple website using ansible and docker on Ubuntu EC2

## Prerequisites

 - An ubuntu instance
 - key pair

## Features

 - Ansible
 - Docker container


## Tasks

> container_image: httpd:latest

> container_name: docker

 - Uses docker container image `httpd:latest` for apache
 - Container name is `docker`
---------------------------------------------------------------------
> ports:

> -"80:80"

 - Host port used is `80` and Container port used is `80`
---------------------------------------------------------------------
>volumes:

>-/var/www/html/mak.tk/:/usr/local/apache2/htdocs/

>-/home/ubuntu/mak.conf:/usr/local/apache2/conf/extra/httpd-vhosts.conf

>-/home/ubuntu/httpd.conf:/usr/local/apache2/conf/httpd.conf

 - Extracts the website to `/var/www/html/mak.tk/` in the Host EC2 and mounted as volume to docker  in `/usr/local/apache2/htdocs/`

 - Custom `httpd.tmp` is copied as `/home/ubuntu/httpd.conf` to Host EC2 and mounted as volume to docker in `/usr/local/apache2/conf/httpd.conf`

 - Custom `virtual_host.tmp` is copied as `/home/ubuntu/mak.conf`  to Host EC2 and mounted as volume to docker in `/usr/local/apache2/conf/extra/httpd-vhosts.conf`
