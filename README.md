# Docker Installation Guide

⚠️ **Warning**: This guide assumes you're using **root** privileges. Use at your own risk.

❗ **Note**: Some Docker containers might use the same ports. Please check the compose file carefully.

---

## Quick Start

Install Docker Engine and Docker Compose plugin with a single command:

```

curl -sSL get.docker.com | sh
```

## Detailed Installation Instructions

### Debian / Ubuntu

#### 1. Update and Install Dependencies

```

apt update
apt install ca-certificates curl
```

#### 2. Add Docker GPG Key

```

sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
chmod a+r /etc/apt/keyrings/docker.asc
```

#### 3. Add Docker Repository

```

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  tee /etc/apt/sources.list.d/docker.list > /dev/null
apt-get update
```

#### 4. Install Docker

```

apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

---

### RHEL / Alma / Rocky / CentOS

#### 1. Install Required Tools

```

yum install -y yum-utils
```

#### 2. Add Docker Repository

```

yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
```

#### 3. Install Docker

```

yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#### 4. Start and Enable Docker

```

systemctl enable docker && systemctl start docker
```

---

### Fedora

#### 1. Install Required Tools

```

dnf -y install dnf-plugins-core
```

#### 2. Add Docker Repository

```

dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
```

#### 3. Install Docker

```

dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#### 4. Start and Enable Docker

```

systemctl enable docker && systemctl start docker
```

---

## Verification

After installation, verify Docker is working properly:

```

docker --version
docker-compose --version
```

---

## Troubleshooting

If you encounter any issues:
1. Check if Docker service is running: `systemctl status docker`
2. Verify your user is in the docker group: `groups`
3. Check Docker logs: `journalctl -u docker.service`

---

> **Tip**: For non-root usage, add your user to the docker group: `sudo usermod -aG docker $USER`