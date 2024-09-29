# PostgreSQL Master-Slave Replication with Pgpool-II Load Balancer

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-11.2-blue.svg) ![Docker](https://img.shields.io/badge/Docker-20.10.7-blue.svg) ![License](https://img.shields.io/badge/License-MIT-green.svg) ![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)

This project demonstrates how to set up PostgreSQL master-slave replication using Docker Compose with Bitnami PostgreSQL images. Pgpool-II is used to handle load balancing across the master and replicas.

## Table of Contents
- [Architecture](#architecture) 📊
- [Services](#services) 🛠️
- [Requirements](#requirements) ✅
- [Usage](#usage) 🚀
- [Environment Variables](#environment-variables) ⚙️
- [Volumes](#volumes) 💾
- [Ports](#ports) 🔌
- [Health Checks](#health-checks) 🔍
- [License](#license) 📜

---

## Architecture
This setup includes:
- **db-master**: Primary PostgreSQL database where all write operations occur.
- **db-slave1** and **db-slave2**: Replicas that are synchronized with the master. They are used for read operations.
- **Pgpool-II**: Load balancer to distribute read queries across the slaves and write queries to the master.

---

## Services

### 1. PostgreSQL Master (`db-master`) 🏗️
The master PostgreSQL database, which handles all write operations.

### 2. PostgreSQL Replica 1 (`db-slave1`) 📖
A read-only replica of the master database. It synchronizes data with the master.

### 3. PostgreSQL Replica 2 (`db-slave2`) 📖
Another read-only replica of the master database.

### 4. Pgpool-II (`pgpool`) ⚖️
Pgpool-II is a middleware that provides load balancing for read queries and ensures high availability by directing write operations to the master.

---

## Requirements

- ✅ **Docker**
- ✅ **Docker Compose**

---

## Usage

1. **Clone the repository:**
    ```bash
    git clone https://github.com/Hisham2000/Database-Replication-PostgreSQL.git
    ```

2. **Navigate to the directory:**
    ```bash
    cd Database-Replication-PostgreSQL
    ```

3. **Start the services:**
    ```bash
    docker-compose up -d
    ```

4. **Verify that the services are running:**
    ```bash
    docker-compose ps
    ```

5. **To stop the services:**
    ```bash
    docker-compose down
    ```

---

## Environment Variables

The Docker Compose file uses several environment variables to configure the PostgreSQL and Pgpool-II services:

- **POSTGRESQL_DATABASE**: The default database to create.
- **POSTGRESQL_USERNAME**: Username for PostgreSQL.
- **POSTGRESQL_PASSWORD**: Password for PostgreSQL.
- **PGPOOL_ENABLE_LOAD_BALANCING**: Enables or disables load balancing.

For more details, refer to the Docker Compose file or the official Bitnami PostgreSQL documentation.

---

## Volumes

The following volumes are used to persist database and Pgpool-II configurations:

- **master_data**: Stores data for the master PostgreSQL instance.
- **slave1_data**: Stores data for the first PostgreSQL replica.
- **slave2_data**: Stores data for the second PostgreSQL replica.
- **pgpool_config**: Stores Pgpool-II configuration files.

---

## Ports

The services are exposed on the following ports:

| Service    | Port (Host) | Port (Container) | Description                 |
|------------|-------------|------------------|-----------------------------|
| Pgpool-II  | 5462        | 5432             | Pgpool-II load balancer      |
| Master DB  | 5463        | 5432             | PostgreSQL master            |
| Slave 1 DB | 5464        | 5432             | PostgreSQL replica 1         |
| Slave 2 DB | 5465        | 5432             | PostgreSQL replica 2         |

---

## Health Checks

Health checks are configured for all services to ensure proper operation.

- **PostgreSQL**: Uses the script `/opt/bitnami/scripts/postgresql/healthcheck.sh` to monitor the status.
- **Pgpool-II**: Pgpool performs internal checks to monitor the state of backend nodes and replication health.

---

## License

📄 This project is licensed under the **[MIT License](LICENSE)**.  
For more details, please refer to the license file included in this repository. 

---

Feel free to customize the repository link, architecture diagram path, and any other details specific to your project!
