# debian-php7
Dockerized php-fpm service, built on top of official [Debian](https://hub.docker.com/_/debian/) images with supervisor.

# Image tags
* thinegan/debian-php7:latest (Debian GNU/Linux 9)

# Installed packages
* [9, stretch, latest (stretch/Dockerfile)](https://github.com/tianon/docker-brew-debian/blob/e8131d071a42b8e88cabbb0aa33023c7b66b7b93/jessie/Dockerfile)

# Image specific:
* php-fpm - v7.2.3

# Config:
* Dependencies Package:
  * mysqli
  * gd
* php.ini setup path: /usr/local/etc/php/conf.d/php.ini

# Run example
```console
$docker pull thinegan/debian-php7
$docker run -d -p 9000:9000 --name testphp thinegan/php7:latest

# Docker compose, example of spinning 1 php-fpm containers with mounted volume from host.
services:
  phpserver1:
    image: thinegan/php7:latest
    container_name: phpfpm1
    hostname: phpserver1
    build: .
    # Exposed to host machines
    ports:
      - "9000"
    volumes:
      - /home/www/public_html/dev.crytera.com:/home/www/public_html/dev.crytera.com
      - ./etc/php/php.ini:/usr/local/etc/php/conf.d/php.ini
```

# Issues
If you run into any problems with this image, please check (and potentially file new) issues on the [thinegan/debian-php7](https://github.com/thinegan/debian-php7) repo, which is the source for this image.

