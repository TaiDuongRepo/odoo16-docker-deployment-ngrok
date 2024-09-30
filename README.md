# Odoo Docker Deployment

This project provides a complete solution for deploying Odoo using Docker, Nginx, Ngrok, and PostgresSQL.

## Project Structure

- **Odoo**: The main Odoo service running on Docker.
- **PostgreSQL**: The database service used by Odoo.
- **Nginx**: The reverse proxy server to manage and optimize traffic.
- **Ngrok**: Provides secure tunnels to access the Odoo service over the internet.

## Folder Structure
└── source
    ├── config
    │   └── odoo.conf
    ├── docker-compose.yml
    ├── Dockerfile
    ├── dump.sql
    ├── requirements.txt
    ├── nginx
    │   ├── default.conf
    │   └── Dockerfile.dev
    └── ngrok.yml

## Setup Environment Variables

In the `/config/odoo.conf` file, you can set the environment variables for the Odoo service. The following are the default environment variables:

```conf
[options]
db_port = 5432
db_user = <db_user>
db_password = <db_password>
db_name = <db_name>
admin_passwd = <admin_passwd>
addons_path = /mnt/extra-addons
```

In the 'docker-compose.yml' file, you can set the environment variables for the Odoo service. The following are the default environment variables:

```yaml
environment:
    - HOST=mydb
    - USER=<db_user>
    - PASSWORD=<db_password>
```

## Ngrok Setup

To use Ngrok, you need to create an account and get an authtoken. You can set the authtoken in the `ngrok.yml` file.

And create a domain, and a edge endpoint in the ngrok dashboard and set the endpoint in the `ngrok.yml` file.

## Usage

To start the Odoo service, run the following command:

```bash
docker-compose up -d
```

For access in the browser, you can use the following URL generated by Ngrok

Example: `https://random-domain.ngrok.io`

## Extra points
Ngrok is a service that provides secure tunnels to access the Odoo service over the internet. making it accessible from the internet without needing to open or NAT ports on your VPS. This is especially useful when you want to expose services behind firewalls or NAT restrictions.

## Author

- [TaiDuongRepo](github.com/TaiDuongRepo)