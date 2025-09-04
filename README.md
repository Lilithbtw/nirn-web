# nirn-web

Configs, scripts, and assets for my self-hosted VM that powers my personal website and cloud (Nextcloud).

## Overview

This repository contains everything to run my self-hosted web stack:

- **Personal Website** – served via Nginx  
- **Nextcloud Instance** – private cloud for files, calendars, and more  
- **Traefik Reverse Proxy** – automatically handles HTTPS with Cloudflare DNS challenge  
- **Docker Compose Configuration** – for managing all services

## Services

- **traefik** – reverse proxy for routing traffic and managing SSL certificates  
- **nginx** – serves the personal website  
- **php-fpm** – PHP backend for the website  
- **nextcloud** – self-hosted cloud application  
- **nextclouddb** – MariaDB database for Nextcloud  
- **redis** – caching for Nextcloud  

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/nirn-web.git
cd nirn-web
```
2. Create a .env file with your Cloudflare API key: (i have a whole guide on how to do it in https://github.com/lilithbtw/cloudflare-ddns-script)
3. fill in the rest of the .env with your specific case
```bash
nano .env
```
### Setup the file structure
```bash
mkdir src
mkdir letsencrypt
touch letsencrypt/acme.json
```
Then start the docker compose:
```bash
docker compose up -d
```
Then drop your static HTML or PHP
```bash
mv /myapp ./src
```
