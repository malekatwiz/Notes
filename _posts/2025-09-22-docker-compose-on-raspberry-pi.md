---
layout: post
title: "Docker & docker-compose on Raspberry Pi OS"
author: "Malek Atwiz"
---

Steps to setup Docker and docker-compose on a Raspberry Pi OS

1. **System Update**:
```Bash
sudo apt update && sudo apt upgrade -y
```

2. **Install Docker**:
```Bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

3. **Run Docker as root-less**:
```Bash
sudo apt-get install -y uidmap
dockerd-rootless-setuptool.sh install
```

4. **Ensure Docker & Docker-Compose are Installed**:
```Bash
docker --version
docker compose version
```
