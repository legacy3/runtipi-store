# Lumina (Lumen)

Lumina is a modern web application built with a PostgreSQL database backend. It provides a robust platform for various web-based functionalities and services.

## Features

- **PostgreSQL Database**: Reliable and scalable database backend
- **Multi-port Support**: Main application on port 1234 with additional services on port 8082
- **Docker-based Deployment**: Easy deployment and management through containers
- **Health Monitoring**: Built-in health checks for database connectivity
- **Persistent Storage**: Data persistence through volume mounts

## Configuration

The application requires a PKCS password for certificate management, which can be configured through the Runtipi interface.

### Database Configuration

Lumina uses PostgreSQL 15.1 Alpine for its database backend with the following default settings:

- Database: `lumina`
- User: `lumina`
- Password: `1` (configurable)

### Ports

- **Main Application**: Port 1234 (web interface)
- **Additional Services**: Port 8082 (extended functionality)

## Storage

Application data is stored in the following directories:

- `/dockershare`: Application shared data directory
- `/postgres_data`: PostgreSQL database files

All data is automatically mapped to your Runtipi app data directory for persistence across container restarts.

## Health Monitoring

The PostgreSQL service includes built-in health checks using `pg_isready` to ensure database availability before starting dependent services.
