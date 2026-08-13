# systemd Cheatsheet

Quick commands for managing services and viewing logs with systemd.

## Services

```sh
sudo systemctl start <service>
sudo systemctl stop <service>
sudo systemctl restart <service>
sudo systemctl reload <service>
```

## Status

```sh
systemctl status <service>
```

## Enable at Boot

```sh
sudo systemctl enable <service>
```

Enable and start immediately:

```sh
sudo systemctl enable --now <service>
```

Disable:

```sh
sudo systemctl disable <service>
```

Disable and stop:

```sh
sudo systemctl disable --now <service>
```

## List Services

```sh
systemctl list-units --type=service

systemctl list-units --type=service --state=running

systemctl list-unit-files --type=service
```

## Failed Units

```sh
systemctl --failed
```

## Logs

```sh
journalctl

journalctl -u <service>

journalctl -u <service> -f

journalctl -u <service> -b
```

Current boot:

```sh
journalctl -b
```

Previous boot:

```sh
journalctl -b -1
```

## User Services

```sh
systemctl --user status <service>

systemctl --user start <service>

systemctl --user enable --now <service>
```

## Unit Files

System unit files are commonly found under:

```text
/etc/systemd/system/
/usr/lib/systemd/system/
```

User units commonly live under:

```text
~/.config/systemd/user/
```

After manually changing unit files:

```sh
sudo systemctl daemon-reload
```

For user units:

```sh
systemctl --user daemon-reload
```
