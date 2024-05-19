# Vaultwarden

Vaultwarden is a lightweight Bitwarden server for self-hosting. It is compatible with most of the Bitwarden clients, including the desktop apps for Windows, macOS, and Linux, as well as the mobile apps for iOS and Android.

Official repository: [dani-garcia/vaultwarden](https://github.com/dani-garcia/vaultwarden)

## Deployment

This deployment uses Docker and Docker Compose. You can deploy it with the following steps:

1. Clone this repository:

   ```bash
    git clone https://github.com/dkadev/vaultwarden
    cd vaultwarden
    ```

2. Create a `.env` file:

   ```bash
   cp .env.template .env
   ```

3. Edit the `.env` file and set the environment variables as needed. See [official wiki](https://github.com/dani-garcia/vaultwarden/wiki/Configuration-overview) for more information.

4. Generate self-signed SSL certificates:

   ```bash
   openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ./certs/vaultwarden.key -out ./certs/vaultwarden.crt
   ```

5. Start the services:

   ```bash
   docker-compose up -d
   ```

6. Access the web interface at `https://domain.local`.
