# wpcli
Useful wp cli commands for every WordPress Developer. This repo will contain all the useful commands that help WordPress developer to speed up the development process.

# How to install wpcli
```
# With Phar file
curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
```

1. How to check wordpress version :question:

:heavy_dollar_sign: wp core version
```
4.9.7
```
2. Check wordpress installation bacis info :question:

:heavy_dollar_sign: wp --info 
```
 /var/www/html/wordpress  wp --info      
OS:	Linux 4.13.0-45-generic #50~16.04.1-Ubuntu SMP Wed May 30 11:18:27 UTC 2018 x86_64
Shell:	/usr/bin/zsh
PHP binary:	/usr/bin/php7.0
PHP version:	7.0.30-0ubuntu0.16.04.1
php.ini used:	/etc/php/7.0/cli/php.ini
WP-CLI root dir:	phar://wp-cli.phar
WP-CLI vendor dir:	phar://wp-cli.phar/vendor
WP_CLI phar path:	/var/www/html/wordpress
WP-CLI packages dir:	
WP-CLI global config:	
WP-CLI project config:	
WP-CLI version:	1.5.1
```

3. Get list of all plugins with status :question:

:heavy_dollar_sign: wp plugin list
```
 /var/www/html/wordpress  wp plugin list
+---------+----------+-----------+---------+
| name    | status   | update    | version |
+---------+----------+-----------+---------+
| akismet | inactive | available | 4.0.3   |
| hello   | inactive | none      | 1.7     |
+---------+----------+-----------+---------+
```

4. Activate a plugin  :question:

:heavy_dollar_sign: wp plugin activate pluginname ( see the name from pugin list as shown in above command)
```
 /var/www/html/wordpress  wp plugin activate hello
Plugin 'hello' activated.
Success: Activated 1 of 1 plugins.
```

5. Check status of a plugin  :question:
```
 /var/www/html/wordpress  wp plugin status hello
Plugin hello details:
    Name: Hello Dolly
    Status: Active
    Version: 1.7
    Author: Matt Mullenweg
    Description: This is not just a plugin, it symbolizes the hope and enthusiasm of an entire generation summed up in two words sung most famously by Louis Armstrong: Hello, Dolly. When activated you will randomly see a lyric from <cite>Hello, Dolly</cite> in the upper right of your admin screen on every page.

```


5. Install a plugin and activate it :question:

:heavy_dollar_sign: wp plugin install woocommerce --activate
```
 /var/www/html/wordpress  wp plugin install woocommerce --activate
Installing WooCommerce (3.4.3)
Downloading installation package from https://downloads.wordpress.org/plugin/woocommerce.3.4.3.zip...
Unpacking the package...
Installing the plugin...
Plugin installed successfully.
Activating 'woocommerce'...
Plugin 'woocommerce' activated.
Success: Installed 1 of 1 plugins.
```

6. Create a new user. :question:

:heavy_dollar_sign: wp user create *username* *useremail*  --role=*rolename*
```
 /var/www/html/woo  wp user create inrsaurabh inrsaurabh@gmail.com  --role=author
Success: Created user 2.
Password: a$hgLg3HeZJsy%sOnsZG!qes

```
