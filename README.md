# Pterodactyl Docker

Pterodactyl Dockerized with Traefik and Hetzner DNS

Welcome to a streamlined way of deploying Pterodactyl Panel and Wings in Docker containers. This project makes the process user-friendly, ensuring your setup is both easy and secure. With Traefik as a reverse proxy, SSL certificates are automatically generated using Hetzner DNS.

**!! NOTE !!** This solution is designed to run either the Panel or Wings on a single machine, not both simultaneously!

# Pterodactyl Panel Installation Guide

This step-by-step walkthrough will assist you in setting up your Pterodactyl panel within a Docker environment. Before you begin, ensure you have the following installed on your system:

- Docker
- Docker Compose
- curl
- unzip
- sudo

## Download and Prepare the Repository

First, download the Pterodactyl Docker repository:

```bash
curl -LJO https://github.com/rattatude/pterodactyl-docker/archive/refs/heads/main.zip
```

Next, unzip the downloaded file and rename the directory for clarity:

```bash
unzip pterodactyl-docker-main.zip
mv pterodactyl-docker-main pterodactyl
cd pterodactyl/panel/
```

## Set Permissions and Configure the Panel

Ensure the correct permissions for essential files:

```bash
sudo chmod 600 data/traefik/acme.json
```

Edit the configuration file to your needs:

```bash
vi .env
```

## Launch the Pterodactyl Panel

Start the Docker container in the background:

```bash
sudo docker compose up -d
```

Optionally, check the container logs for any errors:

```bash
sudo docker compose logs -f
```

## Verify the Panel Setup

Visit the domain you configured earlier in your browser. Please be patient, as it might take a few minutes for the SSL certificate to be generated. Once the panel is up and running, you're ready to proceed.

## Create an Administrative User

Finally, create an administrative user for your Pterodactyl panel:

```bash
sudo docker compose run --rm panel php artisan p:user:make
```

Follow the prompts to set up the administrative account, and you're all set! Your Pterodactyl Panel installation is now complete, and you can begin managing your game servers with ease.

If you encounter any issues or have questions, please feel free to open an issue in this GitHub repository. I am here to assist you. Happy gaming!

# Pterodactyl Wings Installation Guide

This step-by-step walkthrough will assist you in setting up Pterodactyl Wings within a Docker environment. Before you start, make sure you have the following installed on your system:

- Docker
- Docker Compose
- curl
- unzip
- sudo

## Download and Prepare the Repository

Begin by downloading the Pterodactyl Docker repository:

```bash
curl -LJO https://github.com/rattatude/pterodactyl-docker/archive/refs/heads/main.zip
```

Next, unzip the downloaded file and rename the directory for clarity:

```bash
unzip pterodactyl-docker-main.zip
mv pterodactyl-docker-main pterodactyl
cd pterodactyl/wings/
```

## Set Permissions and Configure Wings

Ensure the correct permissions for essential files:

```bash
sudo chmod 600 data/traefik/acme.json
```

Edit the environment and configuration files to your requirements:

```bash
vi .env
vi data/wings/etc/config.yml
```

## Launch Pterodactyl Wings

Start the Docker container in the background:

```bash
sudo docker compose up -d
```

Optionally, check the container logs for any errors:

```bash
sudo docker compose logs -f
```

Your Pterodactyl Wings installation is now running successfully!

If you encounter any issues or have questions, please feel free to open an issue in this GitHub repository. I am here to assist you. Happy gaming!
