# Introduction

This repository provides a `docker-compose.yml` ready-to-use Docker configuration to simplify the deployment of Uptime Kuma, a self-hosted monitoring tool. For comprehensive details about configuring Uptime Kuma in Docker, please refer to the [Uptime Kuma Docker Hub page by Elestio](https://hub.docker.com/r/elestio/uptime-kuma).

## Repository Contents

This repository includes:

- **Docker Compose File**: A `docker-compose.yml` file that configures the Uptime Kuma Docker container. Key features of this setup include:
  - **Persistent Data Storage**: Configures a volume:
    - `uptime-kuma-data` at `/app/data` for storing Uptime Kuma data.

    This ensures that your monitoring data is preserved across container restarts.

## Getting Started

### Important Preliminary Step

Before initiating the setup, please consider the following point:

1. **Important Note on Port Mapping**: The `docker-compose.yml` file contains a port mapping to `127.0.0.1`, limiting access to the localhost only. To make the service accessible from other machines or publicly, change the IP address in the port mapping. For instance, use `0.0.0.0` to bind to all network interfaces, updating the ports line to `- "0.0.0.0:8088:8088"` for broader network access.

### Quick Setup

1. **Clone the Repository**:
   Clone this repository to your local machine using the following Git command:
   ```bash
   git clone https://github.com/ramuyk/docker-uptime-kume.git
   cd docker-uptime-kuma
   ```

2. **Start Uptime Kuma**:
   Navigate to the directory containing your `docker-compose.yml` file and use the following command to start Uptime Kuma:
   ```bash
   docker compose up -d
   ```

3. **Access Uptime Kuma**:
   Open a web browser and navigate to `http://localhost:3001` to access the Uptime Kuma interface. Set up your login credentials during the first access.
