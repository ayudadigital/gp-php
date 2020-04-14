# Generic Platform - PHP Web Application

## Overview

Docker image and docker-compose sample configuration to bring up a PHP web application product to the [Docker Generic Platform (GP)](https://github.com/tpbtools/docker-generic-platform).

## Configuration

The product is formed by one container:

- **webapp**: based on [php:7.4.2-apache-buster](https://hub.docker.com/_/php?tab=tags&page=1&name=7.4.2-apache-buster) docker image.

## Operation

1. Use the `docker-compose.yml.sample` file as your docker-compose configuration file.

2. Install assets with `devcontrol assets-install` and copy your web application files in the `/data/var/www/html` directory.

3. Start with `docker-compose up -d`.

4. Open the url <http://localhost:8080> in a browser to view your application running.

5. Manage backups of your files:

   1. Make a backup executing `docker-compose exec webapp backup`.
   2. Find the current backup within the `/var/backups/gp/webapp/` of the container.
   3. Extract the current backup executing `docker cp $(docker-compose ps -q webapp):/var/backups/gp gp`.

6. Stop the platform with `docker-compose stop`.

You can use this docker piece with the [Docker Generic Platform](https://github.com/tpbtools/docker-generic-platform) project.

## Known issues

None known
