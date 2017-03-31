# VPS

> VPS: Virtual Private Server

+ flexible
+ scalable
+ on demand

## Copying the Public Key to the server

```bash
ssh-copy-id -i ~/.ssh/Backend.pub pearpages@Backend
```

Alternatively, you can paste in the keys using SSH:

```
cat ~/.ssh/id_rsa.pub | ssh user@123.45.56.78 "mkdir -p ~/.ssh && cat >>  ~/.ssh/authorized_keys"
```

## Logging with a Specific Key

```bash
ssh -i ~/.ssh/my_key root@YOUR_SERVER_IP
# exiting conection
exit
```

```bash
less known_hosts
```

## Activity Monitor

```bash
top
```

or use htop

```bash
sudo apt-get htop
```

type <q> to quit

## Update Your Server

```bash
apt-get update
```

## Example

```bash
# virtual box default IP for Host-Only Networks
ping 192.168.56.1
```

```bash
ps -A | grep sshd
```

## Config OpenSSH

```bash
ifconfig -a
```

```bash
sudo vi /etc/network/interfaces
```

```bash
# with dhcp
auto enp0s8
iface enp0s8 inet dhcp
```

```bash
# but we want it with an STATIC IP
auto enp0s8
iface enp0s8 inet static
    address 192.168.56.99
    netmask 255.255.255.0
    gateway 192.168.56.1
```

```bash
sudo vi /etc/ssh/sshd_config
```

## Changing the Hostname

```bash
/etc/hostname
```

## Creating an Alias for your Host Computer

```bash
sudo vi /etc/hosts
```

```bash
192.168.56.99 my-virtual-machine
```

## Starting and Stopping

Stop the network interface eth0:
```ifdown eth0```

Start the network interface eth0:
```ifup eth0```

Don't confuse with the following command, which restarts all the networks services :
```/etc/init.d/networking restart```



