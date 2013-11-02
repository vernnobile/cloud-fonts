The Firefox browser by default will not allow access to webfonts from remote URLs.
Firefox will return a "bad URL or cross-site access not allowed" and fail to load the webfonts.
To remedy this add the code below to the .htacess file into each directory that contains the font family files your are serving;
!if your font directory has no .htaccess file, just create one and add the following;

<FilesMatch "\.(ttf|otf|eot|woff)$">
<IfModule mod_headers.c>
Header set Access-Control-Allow-Origin "*"
</IfModule>
</FilesMatch>


 
