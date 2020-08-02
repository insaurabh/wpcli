
# wpcli
Useful wp cli commands for every WordPress Developer. This repo will contain all the useful commands that help WordPress developer to speed up the development process.

# How to install wpcli
```
# With Phar file
curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
#and 
php wp-cli.phar --info
#and
chmod +x wp-cli.phar
#and
sudo mv wp-cli.phar /usr/local/bin/wp
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

:heavy_dollar_sign: wp plugin activate plugin_name ( see the name from plugin list as shown in above command)
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
 /var/www/html/wordoress  wp user create inrsaurabh inrsaurabh@gmail.com  --role=author
Success: Created user 2.
Password: a$hgLg3HeZJsy%sOnsZG!qes

```

7. Update an user password. :question:

:heavy_dollar_sign: wp user update **user_id**  --user_pass=**new_password**
```
 /var/www/html/wordoress  wp user update 2 --user_pass=your_new_password
Success: Updated user 2.

```

8. Get all theme list. :question:

:heavy_dollar_sign: wp theme list
```
 /var/www/html/wordpress  wp theme list
+-----------------+----------+--------+---------+
| name            | status   | update | version |
+-----------------+----------+--------+---------+
| twentyfifteen   | inactive | none   | 2.0     |
| twentyseventeen | active   | none   | 1.6     |
| twentysixteen   | inactive | none   | 1.5     |
+-----------------+----------+--------+---------+

```

9. Activate a theme. :question:

:heavy_dollar_sign: wp theme activate **themename** ( see name from above list)
```
 /var/www/html/wordpress  wp theme activate twentysixteen
Success: Switched to 'Twenty Sixteen' theme.

```

9. Create child theme. :question:

:heavy_dollar_sign: wp scaffold child-theme **child-theme-name** --parent_theme=**parentthemename** ( see name from above list)
```
 /var/www/html/wordpress  wp scaffold child-theme twentysixteen-child --parent_theme=twentyseventeen
Success: Created '/var/www/html/wordpress/wp-content/themes/twentysixteen-child'.

```

10. Delete a theme. :question:

:heavy_dollar_sign: wp theme delete **themename** ( see name from above list)
```
 /var/www/html/wordpress  wp theme delete **themename**
Deleted '**themename**' theme.
Success: Deleted 1 of 1 themes.
```
11. Flushes rewrite rules ( permalink updates ). :question:

:heavy_dollar_sign: wp rewrite flush
```
 /var/www/html/wordpress  wp rewrite flush
Success: Rewrite rules flushed.
```

12. Get dtabase name with list of tables. :question:

:heavy_dollar_sign: wp db check 
```
 /var/www/html/wordpress  wp db check 
db_name.prefix_tableName                           OK
wppwa.wppwa_comments                               OK
...................................
..................................
Success: Database checked.
```

13. Update siteurl and home url ( search and replace any string) . :question:

:heavy_dollar_sign: wp search-replace 'http://localhost/projectname' 'http://projectname.com' --skip-columns=guid 
```
 /var/www/html/wordpress  wp search-replace 'http://localhost/projectname' 'http://projectname.com' --skip-columns=guid 
+---------------------+-----------------------+--------------+------+
| Table               | Column                | Replacements | Type |
+---------------------+-----------------------+--------------+------+
| wppwa_commentmeta   | meta_key              | 0            | SQL  |
| wppwa_commentmeta   | meta_value            | 0            | SQL  |
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''
 wppwa_options        | option_value           | 2            | PHP |
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''
| wppwa_users         | user_activation_key   | 0            | SQL  |
| wppwa_users         | display_name          | 0            | SQL  |
+---------------------+-----------------------+--------------+------+


Success: Made 8 replacements.
```

 14. How to install Wordpress :question:
```
 - mkdir blog
 - cd blog
 - wp core download
 - wp core config --dbhost=your_host_name --dbname=db_prefix --dbuser=username --dbpass=password
 - wp core install --url=yourwebsite.com --title="Your Blog Title" --admin_name=wordpress_admin_name --admin_password=admin_pwd --admin_email=you@yourwebsite.com
 - chmod 644 wp-config.php
 - chmod 775 uploads/

``` 

> To use next 3 commands include [these commands](https://github.com/insaurabh/wpcli/blob/master/custom-command.md) in your theme.

 15. How to UPDATE an option :question:
```
 - wp option update start_of_weeks 0

``` 

 16. How to DELETE an option :question:
```
 - wp option delete start_of_weeks

``` 

 17. How to ADD an option :question:
```
 - wp option add option_name option_value
 
``` 

# Download, Fork, Commit.

Please Download, Fork, & Commit to add more helpfull commands.
