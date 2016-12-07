# Apache2 (httpd) on Raspberry Pi

#### IMPORTANT: This image is not ready yet! There is still a lot to do.

Todo:
* own (certified) SSL certificates
* Optional: Some change in configuration files (example: http to https forwarding, own conf/mods/ssl (folder))

### Image Info
* without PHP
* https://httpd.apache.org/

### How to use this image
* ``` docker pull tobi312/rpi-apache2 ```
* Optional: ``` mkdir -p /home/pi/html ```
* ``` docker run --name httpd -p 80:80 -p 443:443 -v /home/tobias/html:/var/www/html --link some-php-fpm-container:phphost -e ENABLE_PROXY_FCGI=true -e ENABLE_PROXY_HTML=true -e ENABLE_SSL=true -e ENABLE_REWRITE=true -e ALLOWOVERRIDE=true -d tobi312/rpi-apache2 ``` 

or build it yourself
* ``` git clone https://github.com/TobiasH87Docker/rpi-apache2.git && cd rpi-apache2 ```
* Optional: ``` mkdir -p /home/pi/html ```
* ``` docker build -t tobi312/rpi-apache2 . ``` 
* ``` docker run --name httpd -p 80:80 -p 443:443 -v /home/tobias/html:/var/www/html --link some-php-fpm-container:phphost -e ENABLE_PROXY_FCGI=true -e ENABLE_PROXY_HTML=true -e ENABLE_SSL=true -e ENABLE_REWRITE=true -e ALLOWOVERRIDE=true -d tobi312/rpi-apache2 ``` 
* http://localhost 

### You need PHP (PHP-FPM)?, see here: 
* [DockerHub](https://hub.docker.com/r/tobi312/rpi-php/)
* [GitHub](https://github.com/TobiasH87Docker/rpi-php)

### This Image on
* [DockerHub](https://hub.docker.com/r/tobi312/rpi-apache2/)
* [GitHub](https://github.com/TobiasH87Docker/rpi-apache2)
