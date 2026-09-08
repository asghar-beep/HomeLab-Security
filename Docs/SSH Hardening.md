# SSH Hardening

## Objective

Improve the security of remote access to my Ubuntu Server by replacing password-based authentication with SSH key authentication.

## Environment

- Client: Windows 11 (PowerShell / OpenSSH)
- Server: Ubuntu Server
- Algorithm: ED25519

## Configuration

### 1. Generated an SSH key pair

Generated an ED25519 key pair on the Windows client using `ssh-keygen`.

### 2. Installed the public key

Added the public key to:

```text
~/.ssh/authorized_keys
```

### 3. Secured file permissions

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

### 4. Disabled password authentication

Edited `/etc/ssh/sshd_config`:

```text
PasswordAuthentication no
PubkeyAuthentication yes
```

### 5. Verified the configuration

Validated the SSH configuration before restarting the service using:

```bash
sudo sshd -t
```

Successfully connected from the Windows PC using the SSH key protected by a passphrase.

## Security Benefits

- Eliminates password-based SSH logins
- Reduces brute-force attack risk
- Uses modern ED25519 public-key cryptography
- Protects the private key with a passphrase

## Skills Demonstrated

- SSH
- Linux administration
- Public-key authentication
- File permissions
- Server hardening
- Troubleshooting
