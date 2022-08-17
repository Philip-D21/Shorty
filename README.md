# How to make this for yourself 📖

- Must install PHP version (FOR WINDOWS) & (FOR MAC) Both
- Tutorial - https://www.youtube.com/watch?v=mVBe75aGBHQ
- PHP version used -> ( 8.1.9 )


- Must install xampp (FOR WINDOWS) & MAMP (FOR MAC) 
- Tutorial - https://www.youtube.com/watch?v=at19OmH2Bg4
- MySQL version used -> ( 8.0.29 )

-------*---------*----------

Step -1   Download zip file 

Step -2   unzip it & Rename folder from "tiny-main" to "tiny"

Step -3   Put tiny folder inside 

          /Applications/MAMP/htdocs/  folder  (FOR MAC)
          C:/xampp/htdocs/            folder  (FOR WINDOWS)

Step -4   Set below snippet inside /Applications/MAMP/htdocs/tiny/env.php. file (FOR MAC & having MAMP)
          
            <?php
                $env_server = "localhost";
                $env_username = "root";
                $env_password = "root";
                $env_database = "tiny";
                $env_port = "8889";
            ?>

Step -4   Set below snippet inside htdocs/tiny/env.php. file (FOR WINDOWS & XAMPP)
          

            <?php
                 $env_server = "localhost:3306";
                 $env_username = "root";
                 $env_password = "";
                 $env_database = "tiny";
                 $env_port = "3306";
            ?>

Step -5   Create ".htaccess" file inside htdocs/tiny/ and Paste below code snippet.(FOR MAC & having MAMP)

                ErrorDocument 404 http://localhost:8888/tiny/404.php

                RewriteEngine On
                RewriteCond %{REQUEST_FILENAME} !-d
                RewriteCond %{REQUEST_FILENAME}\.php -f
                RewriteRule ^(.*)$ $1.php [NC,L]


                RewriteEngine On

                RewriteCond $1 !^(index\.php)
                RewriteCond %{REQUEST_FILENAME} !-f
                RewriteCond %{REQUEST_FILENAME} !-d
                RewriteRule ^(.*)$ index.php?/$1 [L]
                
                
Step -5   Create ".htaccess" file inside htdocs/tiny/ and Paste below code snnipet.(FOR WINDOWS)

                ErrorDocument 404 http://localhost/tiny/404.php

                RewriteEngine On
                RewriteCond %{REQUEST_FILENAME} !-d
                RewriteCond %{REQUEST_FILENAME}\.php -f
                RewriteRule ^(.*)$ $1.php [NC,L]


                RewriteEngine On

                RewriteCond $1 !^(index\.php)
                RewriteCond %{REQUEST_FILENAME} !-f
                RewriteCond %{REQUEST_FILENAME} !-d
                RewriteRule ^(.*)$ index.php?/$1 [L]
                
Step -6   Change the file content inside tiny/htdocs/siteName.php

          1) FOR MAC & MAMP
                <?php
                    $siteName = "http://localhost:8888/tiny/";
                ?>
                
          2) FOR Windows
                <?php
                    $siteName = "http://localhost/tiny/";
                ?>
                
Step -7   Start Apache & MySQL server in XAMPP Panel or MAMP Panel

Step -8   To Setup the database, open 

          localhost:8888/phpmyadmin    (FOR MAC & MAMP)
          localhost/phpmyadmin         (FOR WINDOWS & XAMPP)

Step -9   Create New Database 

Step -10   Database name  "tiny"

Step -11   Import Database from "htdocs/tiny/tiny.sql" directory . 

           tiny.sql (db file)

Step -12   Run in browser 

          localhost:8888/tiny/     (FOR MAC)
          localhost/tiny/          (FOR WINDOWS)

