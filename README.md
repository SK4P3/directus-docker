# Directus Docker Compose with Nginx

This repository provides a Docker-based setup for running Directus with multiple environments behind an Nginx reverse proxy.

## What's Included

- Docker Compose file
- Nginx conf to route to different Directus backends

## Usage

### Single Instance

1. Create a new directus instance root folder `cp ./directus/ ./directus-one/`
2. Go in folder `cd directus-one`
3. Run `docker-compose up -d`

### Multiple Instances

To run multiple instances configure each instance on its own port by changing `80:8055` to `8084:8055` or something similar.

Use the included nginx config template to route to the instances accordingly! In the template there are 2 instances on ports 8084 and 8085 preconfigured. Feel free to add more!

## Common Problems

If you get an error where directus is not allowed to access the `./uploads` or `./database` folder run `chmod 777 uploads/` and `chmod 777 database/` 