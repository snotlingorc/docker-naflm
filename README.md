# docker-naflm
docker containers for running the naflm

https://github.com/TheNAF/naflm

## To use:
build either or both the php5 and php7 docker containers.
They are standard php-apache with the gd and mysqli libraries.

> cd images/php7

> docker build -t naflm/php7 .

> cd ../../

> docker-compose up

Normally you would want to ingest the naflm code into the container.
These containers are currently being used to test changes to the naflm
code on both php5 and php7, so the ingestion has not been done yet.

To see the naflm in action, put the naflm code in the src folder.
Overwrite the setting.php file with the one in the root of this project.

Browse over to http://localhost:8080/install.php and start working with the software.

## Options:
 To use php5, build php5 as you did php7.
 edit the docker-compose.yml file and change the line :
> image: naflm/php7

 to
> image: naflm/php5

 docker-compose up

 (if you already have it running, "docker-compose down" first.)

## Future:
Change the docker-compose file to use secrets, instead of hardcoding.
For testing purposes this is ok.