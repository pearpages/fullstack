# VPS

> VPS: Virtual Private Server

+ flexible
+ scalable
+ on demand

## SSH

```bash
ssh user123@45.35.24.541
```

+ username/password
+ ssh key (public key authentication)

## Creating an SSH Key

```bash
cd ~/.ssh/
ssh-keygen -t rsa
```

## Copying the Public Key to the server

```bash
ssh-copy-id -i ~/.ssh/Backend.pub pearpages@Backend
```

Alternatively, you can paste in the keys using SSH:

```bash
# write the contents of the public key and pipe it to the next command
# creat the folder if doesn't exist
# and appends the key in the file authorized_keys
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

Change PermitRootLogin to no

```bash
sudo service ssh restart
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
```
ifdown eth0
```

Start the network interface eth0:
```
ifup eth0
```

Don't confuse with the following command, which restarts all the networks services :

```
/etc/init.d/networking restart
```

## Add Users

```bash
# this user doesn't have access to sudo
adduser $USERNAME
```

Add the user to the group sudo

```bash
# <a> stands for "add"
# <G> stands for "Group"
# "sudo" is the group of "sudoers"
usermod -aG sudo $USERNAME
```

Change of user

```bash
su $USERNAME
```

Check if the user has or not access to sudo trying to read a file

```bash
sudo cat /var/log/auth.log
```

