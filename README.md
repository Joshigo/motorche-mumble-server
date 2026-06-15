# Mumble Server Docker Compose

This repository contains a simple `docker-compose.yaml` configuration to quickly spin up a Mumble voice chat server using the official Docker image.

## Quick Start

1. **Configure your password**:
   You must set a password for your server. Create a `.env` file in the same directory as the `docker-compose.yaml` (you can copy the `.env.example` file if you have one) and set your password:
   
   ```env
   MUMBLE_PASSWORD=your_secure_password_here
   ```

2. **Start the server**:
   Run the following command in your terminal to start the Mumble server in the background:
   
   ```bash
   docker-compose up -d
   ```

## Configuration

The server settings can be adjusted within the `docker-compose.yaml` file under the `environment` section:

* `MUMBLE_SERVERNAME`: The display name of your server (e.g., "Servidor Mumble").
* `MUMBLE_MAXUSERS`: The maximum number of concurrent users allowed (Default: 50).
* `MUMBLE_BANDWIDTH`: Maximum bandwidth per user in bits per second (Default: 72000).
* `MUMBLE_PASSWORD`: Sourced dynamically from the `.env` file.

## Data Persistence

User data, channels, and server configuration are persistently saved in the `./mumble-data` directory on your host machine. This ensures your data is safe and will not be lost when the Docker container is restarted, updated, or removed.
