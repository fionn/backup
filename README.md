# Backups

## Initialise

Initialise the repository with

```sh
export BORG_REPO=user@host:backup/borg/$HOSTNAME.home.$USER
borg init -e keyfile-blake2 --progress --remote-path=borg1
```
where the `--remote-path` argument may be skipped, depending on the remote.

## Link

* Ensure `systemctl --user show-environment` looks correct,
* link unit files with `ln -rs service/backup.* ~/.config/systemd/user/`.

## Enable

```sh
systemctl --user enable backup.timer
```
