## How can you connect to a remote server?

To connect to a remote terminal you can use secure shell protocol (ssh) command.
```bash
ssh username@remoteIp
```
## Explain ssh command with and without passwords

1. If you connect to a remote first server with ssh, you will first be asked to confirm the server's authentication. Once you enter yes, than you will be asked to provide a password. When you enter password, it will not be visible but it will be entered.

2. If you do not want to use password, you can use key-based authentication.
* First generate an SSH key on your local machine with `ssh-keygen -t rsa`command.
* Then copy the generated public key and send it to the remote server with the `ssh-copy-id user@remoteIP`
* Now you can simply run `ssh user@remotIP`command to access to remote server without password.

## How can you manege services?

Depending on the Linux distribution, we can you either service or systemctl commands to manage services.

* service httpd start
* systemctl start httpd

## What is the difference between starting and enabling services?

Starting a servcie is a one time job which starts the service.
Enabling a service makes sure that the service is started each time the machine boots up.
So if you start a service but do not ebale it, you will have to manually start it if your computer is rebooted.

## How can you see how much disk space you have?

By running `df -h`command

# How can you see your IP address?
There are multiple ways to do that
* ip addr show
* curl ifconfig.me
* ifconfig
