# WordPress Project

The idea is that one would use this repository as a jumping off point for WordPress development. Basically you clone or fork the repo. Set the appropriate environment variables or modify the docker-compose.yml file and run `docker-compose up` to start your docker servers to host your WordPress project in.

The site runs by default on [http://localhost:8000](http://localhost:8000). Change line 26 to adjust the port number.

## Restore a WP Website

First, place database script in the root of the project with the name db.sql and uncomment lines 11 and 12 in docker-compose.yml. Make sure the db.sql file starts with a use command with the database name from line 7.

```bash
USE wordpress;
```

Copy the plugins directory from the production site into the root of the project and uncomment line 23.

Copy the uploads directory from the projection site into the root of the project and uncomment line 24.

Replace the themes directory in the root of the website with a copy from the production site.

## Change the site url

Remember to replace database, username, password, or url if you changed them in the script below.

```bash
docker exec -it wordpress-project_db_1 /bin/bash
/usr/bin/mysql -uwordpress -pchangeme wordpress
UPDATE wp_options SET option_value = 'http://localhost:8000' WHERE option_id IN (1, 2);
exit
exit
```
