# Docker Overview

## Objective

Deploy and manage self-hosted applications using Docker on an Ubuntu Server as part of my cybersecurity home lab.

## Environment

- Host OS: Ubuntu Server 26.04.1 LTS
- Docker Version: 29.8.0
- Architecture: x86_64

## Purpose

Docker allows applications to run inside isolated containers without affecting the host operating system. This makes deploying services easier, more consistent, and easier to maintain.

## Running Containers

| Container | Purpose |
|---|---|
| Trilium | Notes and documentation |
| Immich PostgreSQL | Database for Immich |
| Immich Redis | Cache service |
| Crafty Controller | Minecraft server management |
| Wazuh Manager | SIEM management |
| Wazuh Indexer | Log storage and search |
| Wazuh Dashboard | Security monitoring interface |

## Docker Commands Used

### Check Docker version

```bash
docker --version
```

### View running containers

```bash
sudo docker ps
```

### View all containers

```bash
sudo docker ps -a
```

### View resource usage

```bash
sudo docker stats --no-stream
```

### View disk usage

```bash
sudo docker system df
```

## Skills Demonstrated

- Docker
- Container management
- Resource monitoring
- Linux system administration
- Self-hosted infrastructure
