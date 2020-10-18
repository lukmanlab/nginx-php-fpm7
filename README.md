# How to build own image Nginx + PHP-FPM 7
Just exercise to build own image nginx + php-fpm with Linux Alpine - Latest base image.

## What is in the Image ?
- Nginx
- PHP-FPM
- Supervisord

## How to build ?

Clone this repository:
```
git clone https://github.com/lukmanlab/nginx-php-fpm7.git
```

Build image:
```
docker build -t lukmanlab/nginx-php-fpm7 . --no-cache
```

Note:
  - change the image name `lukmanlab/nginx-php-fpm7` with the name that you want.

## Run

Below is an example run command, change it with your options that you want.
```
docker run -itd --rm -p 8080:80 lukmanlab/nginx-php-fpm7
```

## Run with mounting data / copying the web template to the Container

The location of document-root nginx is at `/var/lib/nginx/html`, so you can use it to mount yor web template or index file php to that location.
```
docker run -itd -p 8080:80 -v $PWD/web:/var/lib/nginx/html lukmanlab/nginx-php-fpm7
```

## Reference
- [Wiki Alpine](https://wiki.alpinelinux.org/wiki/Nginx_with_PHP#Configuration_of_PHP7)