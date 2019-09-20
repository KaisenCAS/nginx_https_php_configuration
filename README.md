# nginx_https_php_configuration
This repository contain example file configuration for Nginx server with HTTPS and PHP-FPM.

Can you take this file for example for all your configurations, and change tls certificate directory, log directory and root directory for adapte in your configuration.

In Debian 10 distributions, for use this file, you are install nginx and php-fpm with this commands : 

sudo apt-get update && sudo apt-get install nginx php7.3-fpm -y 

Enabled service on server boot with as commands :

sudo systemctl enable php7.3-fpm
sudo systemctl enable nginx

And add this file in /etc/nginx/sites-available folder, and create symbolic link in ../sites-enabled with a command : 

sudo ln -s /etc/nginx/sites-availbale/thisfile /etc/nginx/sites-enabled for activate your vhost. 

Testing this file with this PHP code, create file in /var/www/html (or your directory choice with www-data owner) : 

<?
phpinfo();
?>

All PHP info should be displayed, otherwise check the php7.3-fpm.sock in the /var/run/php folder.

If the .sock is not present, start the service with the command :

sudo systemctl start php7.3-fpm




