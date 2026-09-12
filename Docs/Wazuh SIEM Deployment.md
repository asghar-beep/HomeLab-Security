# Wazuh SIEM Deployment

## Objective

Deploy a Security Information and Event Management (SIEM) platform using Docker to monitor Windows endpoints and collect security events.

## Environment

- Ubuntu Server 26.04.1 LTS
- Docker Compose
- Wazuh 4.14.1
- Windows 11 Endpoint (Ash-PC)

## Architecture

Windows PC (Wazuh Agent)

↓

Wazuh Manager

↓

Wazuh Indexer

↓

Wazuh Dashboard

## Installation Steps

### Clone the repository

```bash
git clone https://github.com/wazuh/wazuh-docker.git -b v4.14.1
```

### Navigate to the deployment

```bash
cd ~/wazuh-docker/single-node
```

### Generate TLS certificates

```bash
sudo docker compose -f generate-indexer-certs.yml run --rm generator
```

### Validate Docker Compose

```bash
sudo docker compose config --quiet
```

### Deploy Wazuh

```bash
sudo docker compose up -d
```

## Verification

Verified that all three services were running:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

Confirmed that the Indexer responded securely over HTTPS and required authentication.

## Windows Endpoint

A Windows 11 device was onboarded using the Wazuh Agent and successfully appeared as an **Active** endpoint in the dashboard.

## Skills Demonstrated

- SIEM deployment
- Docker Compose
- Endpoint monitoring
- Log collection
- TLS certificate generation
- Security monitoring

**Reference:** Official Wazuh installation guide. <Cite ref=turn0search1/>