# Servers

+ Nginx (reverse proxy, http server)
+ node

> **NGINX** is a free, open-source, high-performance HTTP server and reverse proxy, as well as an IMAP/POP3 proxy server. NGINX is known for its high performance, stability, rich feature set, simple configuration, and low resource consumption.

## Nginx (engine x)

Previously you have to deactivate apache if it's running on your server:

```bash
sudo systemctl stop apache2.service
```

Prevent apache to start at boot:

```bash
sudo systemctl disable apache2.service
```

```bash
sudo apt update
sudo apt upgrade
```

```bash
sudo apt-get install nginx
sudo service nginx start
```

## Default Nginx Configuration

```bash
sudo cat /etc/nginx/sites-available/default
```

## Git

```bash
sudo apt-get install git
```

## Node

```bash
sudo apt-get install nodejs
```

In Ubuntu you run node with 'nodejs' not 'node'.

## Npm

```bash
sudo apt-get install npm
```

