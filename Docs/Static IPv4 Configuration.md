# Static IPv4 Configuration

## Objective

Configure the Ubuntu Server with a permanent IPv4 address to ensure reliable connectivity for SSH, Samba, Docker services, and Wazuh.

## Network Configuration

| Setting | Value |
|---|---|
| Interface | enp3s0 |
| IPv4 Address | 192.168.1.109 |
| Subnet | 255.255.255.0 (/24) |
| Gateway | 192.168.1.4 |
| DNS | 1.1.1.1, 8.8.8.8 |

## Netplan Configuration

```yaml
network:
  version: 2
  renderer: networkd

  ethernets:
    enp3s0:
      dhcp4: no
      addresses:
        - 192.168.1.109/24
      routes:
        - to: default
          via: 192.168.1.4
      nameservers:
        addresses:
          - 1.1.1.1
          - 8.8.8.8
```

## Safe Deployment

The network configuration was tested using:

```bash
sudo netplan try
```

After confirming SSH connectivity from a second terminal, the configuration was accepted permanently.

## Verification

```bash
ip addr show enp3s0
ip route
```

The server retained the static IPv4 address and continued providing SSH, Samba, Docker, and Wazuh services without interruption.

## Skills Demonstrated

- Linux networking
- Netplan
- Static IPv4 configuration
- Default gateway configuration
- DNS configuration
- Safe remote network administration
