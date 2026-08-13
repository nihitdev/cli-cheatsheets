# SSH Cheatsheet

Quick commands for SSH connections, keys, file transfers, and port forwarding.

## Connect

```sh
ssh user@host

# Custom port
ssh -p 2222 user@host

# Specific key
ssh -i ~/.ssh/id_ed25519 user@host
```

## Generate a Key

```sh
ssh-keygen -t ed25519
```

With a comment:

```sh
ssh-keygen -t ed25519 -C "you@example.com"
```

## Copy Key to Server

```sh
ssh-copy-id user@host
```

## SSH Agent

```sh
eval "$(ssh-agent -s)"

ssh-add ~/.ssh/id_ed25519

ssh-add -l
```

## Config

SSH config:

```text
~/.ssh/config
```

Example:

```text
Host myserver
    HostName 192.168.1.100
    User nihit
    Port 22
    IdentityFile ~/.ssh/id_ed25519
```

Then simply:

```sh
ssh myserver
```

## Run Remote Command

```sh
ssh user@host "uname -a"

ssh user@host "uptime"
```

## SCP

Upload:

```sh
scp file.txt user@host:/remote/path/
```

Download:

```sh
scp user@host:/remote/file.txt .
```

Directory:

```sh
scp -r directory user@host:/remote/path/
```

## Local Port Forwarding

```sh
ssh -L 8080:localhost:80 user@host
```

## Debug Connection

```sh
ssh -v user@host
```

More verbosity:

```sh
ssh -vvv user@host
```
