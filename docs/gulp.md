# Gulp

```bash
sudo mkdir -p /usr/local/lib/node_modules
```

```bash
npm config get prefix
# should print /usr/local
```

```bash
sudo chown -R $(whoami) $(npm config get prefix)/{lib/node_modules,bin,share}
```

# Forever

> **Forever** a process manager that keeps a process running indefenitely.

```bash
forever start app.js
forever list
forever stopall
forever stop <id>
```

```
sudo chown -R $USER /var/log/forever
```

```bash
forever start app.js >> /var/log/forever.log
```

## Tail

```bash
sudo tail -f /var/log/auth.log
```