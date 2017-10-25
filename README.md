# Simple-Url-Shortener
Simple php script for shortening URLs. Made for webservers with multiple usable domains.
## Requirements:
- #### Apache/Nginx
- #### PHP
- #### .html / .php url rewriting
- #### Read/write permissions in that directory

## How to rewrite .html / .php (Apache Version)
- #### Change This line in your apache config file (Where your web directory is) `AllowOverride None` to `AllowOverride All`
- #### In the directory where the URL shortener is, make a file called `.htaccess` and put insert this text into it and save it:
```
<IfModule mod_rewrite.c>
RewriteEngine on

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}.php -f
RewriteRule ^(.*)$ $1.php
#RewriteRule ^([a-z]+)\/?$ $1.php [NC]


RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}.html -f
RewriteRule ^(.*)$ $1.html
#RewriteRule ^([a-z]+)\/?$ $1.html [NC]

</IfModule>
```
