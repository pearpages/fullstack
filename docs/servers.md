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

But we can create a symbolic link:

```bash
sudo ln -s /usr/bin/nodejs /usr/bin/node
```

## Npm

```bash
sudo apt-get install npm
```

## Ruby

```bash
sudo apt-get install ruby-full
```

```bash
sudo gem install bundler
```

## Changing the Ownership of the /var/www folder

```bash
# $USER is not a placeholder here
sudo chown -R $USER:$USER /var/www
```

## Changing Nginx Configuration

```bash
sudo vi /etc/nginx/sites-available/default
sudo service nginx restart
```

To proxy an app using a specific port e.g.:

```bash
location / {
    proxy_pass http://127.0.0.1:/3001/;
}
```