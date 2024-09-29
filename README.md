# Database Replication with Pgpool-II & PostgreSQL with Docker Compose 🚀

![Docker](https://img.shields.io/badge/docker-ready-blue)
![PostgreSQL](https://img.shields.io/badge/postgresql-v14-blue)
![Pgpool-II](https://img.shields.io/badge/pgpool--ii-ready-yellowgreen)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

Easily set up **Pgpool-II** and **PostgreSQL** using Docker Compose for load balancing, connection pooling, and high availability.
---

## 📋 Table of Contents

- [🌟 Features](#-features)
- [⚙️ Requirements](#-requirements)
- [🚀 Quick Start](#-quick-start)
- [🗂️ Folder Structure](#️-folder-structure)
- [🔧 Docker Compose Services](#-docker-compose-services)
- [📊 Usage](#-usage)
  - [Connecting to Pgpool-II](#connecting-to-pgpool-ii)
  - [Volumes](#volumes)
  - [Monitoring](#monitoring)
- [🐞 Common Issues](#-common-issues)
- [📝 License](#-license)
- [📤 Pushing to GitHub](#-pushing-to-github)

---



## 🌟 Features

- **Pgpool-II** for load balancing PostgreSQL databases
- Multiple PostgreSQL nodes for high availability
- Seamless Docker Compose integration
- Ready to use with minimal configuration

---

## ⚙️ Requirements

Before starting, make sure you have the following installed:

- [Docker](https://docs.docker.com/get-docker/) 🐳
- [Docker Compose](https://docs.docker.com/compose/install/) 📦

---
## 🚀 Quick Start

To get this project running locally, follow these steps:

1. **Clone the repository**:
    ```bash
    git clone [https://github.com/yourusername/Database-Replication-PostgreSQL.git](https://github.com/Hisham2000/Database-Replication-PostgreSQL.git)
    cd Database-Replication-PostgreSQL
    ```

2. **Start the services**:
    ```bash
    docker-compose up -d
    ```

3. **Verify the logs**:
    ```bash
    docker-compose logs pgpool
    ```

---

---

## 🗂️ Folder Structure

```bash
📦 Database-Replication-PostgreSQL
├── 📄 docker-compose.yml    # Define services for Docker Compose
└── 📄 README.md             # Project documentation
```
