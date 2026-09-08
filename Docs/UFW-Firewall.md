# UFW Firewall Configuration

## Objective

Secure the Ubuntu Server by configuring a host-based firewall using UFW (Uncomplicated Firewall).

## Default Policy

- Incoming connections: Deny
- Outgoing connections: Allow
- Firewall logging: Low

## Allowed Services

| Service | Port |
|---|---|
| OpenSSH | 22/TCP |
| Samba | 137-138/UDP |
| Samba | 139, 445/TCP |

## Commands Used

```bash
sudo ufw allow OpenSSH
sudo ufw allow Samba
sudo ufw enable
sudo ufw status verbose
```

## Verification

Verified that the firewall allows SSH and Samba while denying all other incoming connections by default.

## Skills Demonstrated

- UFW firewall
- Network security
- Port management
- Linux administration
- Secure server configuration
