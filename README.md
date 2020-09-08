# WordPress Project

The idea is that one would use this repository as a jumping off point for WordPress development. Basically you clone or fork the repo. Set the appropriate environment variables or modify the docker-compose.yml file and run `docker-compose up` to start your docker servers to host your WordPress project in.

The site runs by default on [http://localhost:8000](http://localhost:8000). Change lines 21 and 27 to adjust the port number.

## Restore a WP Website

First, place database script in the root of the project with the name db.sql and uncomment lines 11 and 12 in docker-compose.yml. Make sure the db.sql file starts with a use command with the database name from line 7.

```bash
USE wordpress;
```

Copy the plugins directory from the production site into the root of the project and uncomment line 23.

Copy the uploads directory from the projection site into the root of the project and uncomment line 24.

Replace the themes directory in the root of the website with a copy from the production site.
