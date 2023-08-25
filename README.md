Docker Documentation

STEP 1 : Build Container image - phpmyadmin1

        C:\Users\DevIT\Desktop\php-docker-full-stack-main> docker-compose up --build

STEP 2 : Run the docker Container

        C:\Users\DevIT\Desktop\php-docker-full-stack-main> docker-compose up -d

STEP 3 : PHP Document root connect in command line

        C:\Users\DevIT\Desktop\php-docker-full-stack-main>docker exec -it --user root pma-phpmyadmin-1 /bin/bash  

STEP 4 : Mysql connection in command line

      STEP 4 .1 : C:\Users\DevIT\Desktop\php-docker-full-stack-main> docker-compose exec db mysql -u root -p

      STEP 4 .2 :

            docker ps 

            docker exec -it dockerfile_demo-absolutelywhatever-1 bash  

STEP 5 : Sql file copy in command line
        
        STEP 5:1 : C:\Users\DevIT\Desktop\php-docker-full-stack-main>docker cp dump\dockerExample.sql pma-phpmyadmin-1:/dockerExample.sql

        STEP 5:2 : docker cp dump\dockerExample.sql pma-phpmyadmin-1:/var/lib/dockerExample.sql

STEP 6 : Import Sql file copy in command line

        STEP 5:1 : docker exec -i pma-phpmyadmin-1 mysql -u root -ptest dockerExample < dump/dockerExample.sql

        STEP 5:2 : docker exec -it --user root pma-phpmyadmin-1 mysql -u root -ptest dockerExample < dump/dockerExample.sql



PHP Run URL : http://localhost:9000/index.php

host     : mysql_db
Username : root
Password : root
DB       : students

PHPMyAdmin URL : http://localhost:9001/index.php

Server   : mysql_db
Username : root
Password : root

Docker ERROR Showing and below mention the solving issuse  
------------------------------------------------------------

Requirements: 
* Docker 

To run this code, run command: `docker-compose up` from the shell within the directory of this project after cloning it. 

If you get the error: `Fatal error: Uncaught Error: Call to undefined function mysqli_connect() in /var/www/html/index.php:3 Stack trace: #0 {main} thrown in /var/www/html/index.php on line 3`

Open the interactive terminal with your docker container that's running the `www` service and run the command: `docker-php-ext-install mysqli && docker-php-ext-enable mysqli && apachectl restart`
