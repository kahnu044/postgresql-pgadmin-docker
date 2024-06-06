# PostgreSQL and pgAdmin Docker Setup

This repository contains a Docker Compose configuration to set up a PostgreSQL database and pgAdmin for database management.

## Getting Started

### Prerequisites

- Docker
- Docker Compose

### Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/kahnu044/postgresql-pgadmin-docker
   cd postgresql-pgadmin-docker
   ```

2. **Copy the `.env.example` to `.env` file**

   ```bash
   cp .env.example .env
   ```

   Adjust the values as needed.

3. **Start the services**

   Run the following command to start the PostgreSQL and pgAdmin services:

   ```bash
   docker-compose up -d
   ```

4. **Access pgAdmin**

   Open your web browser and go to `http://localhost:<PGADMIN_PORT>` (default is `http://localhost:8080`).

   Log in with the email and password specified in the `.env` file (`kahnu044@admin.com` and `kahnu044` by default).

5. **Connect pgAdmin to PostgreSQL**

   In pgAdmin, add a new server with the following details:

   - **Name**: Any name you prefer
   - **Host**: `db`
   - **Port**: `5432`
   - **Username**: The value of `DB_USERNAME` from your `.env` file
   - **Password**: The value of `DB_PASSWORD` from your `.env` file

## Configuration

- **PostgreSQL Database**:

  - **Host**: `localhost`
  - **Port**: The value of `POSTGRES_PORT` from your `.env` file (default: `15432`)
  - **Database Name**: The value of `DB_NAME` from your `.env` file (default: `root`)
  - **Username**: The value of `DB_USERNAME` from your `.env` file (default: `root`)
  - **Password**: The value of `DB_PASSWORD` from your `.env` file (default: `root`)

- **pgAdmin**:
  - **URL**: `http://localhost:<PGADMIN_PORT>` (default: `http://localhost:8080`)
  - **Email**: The value of `PGADMIN_EMAIL` from your `.env` file (default: `kahnu044@admin.com`)
  - **Password**: The value of `PGADMIN_PASSWORD` from your `.env` file (default: `kahnu044`)

## Notes

- The `docker-compose.yml` file is configured to use the versions specified in the `.env` file. If no version is specified, it defaults to the latest version.
- The PostgreSQL data is persisted in a Docker volume named `db_data`.

## Author

[Kahnu Charan Swain](https://github.com/kahnu044)



