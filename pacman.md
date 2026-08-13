# pacman Cheatsheet

Quick package-management commands for Arch Linux and Arch-based distributions.

## Update System

```sh
sudo pacman -Syu
```

Synchronizes repositories and upgrades installed packages.

## Install

```sh
sudo pacman -S package
```

Multiple packages:

```sh
sudo pacman -S git neovim ripgrep fd
```

## Search

```sh
# Search repositories
pacman -Ss package

# Search installed packages
pacman -Qs package
```

## Package Information

```sh
# Repository package
pacman -Si package

# Installed package
pacman -Qi package
```

## Remove

```sh
# Remove package
sudo pacman -R package

# Remove package and unused dependencies
sudo pacman -Rns package
```

## Orphans

List orphaned packages:

```sh
pacman -Qdt
```

Remove all currently detected orphans:

```sh
sudo pacman -Rns $(pacman -Qdtq)
```

Check the list before removing anything.

## Files

```sh
# List files owned by installed package
pacman -Ql package

# Find which installed package owns a file
pacman -Qo /path/to/file
```

Search repository file databases:

```sh
pacman -F filename
```

Refresh file databases:

```sh
sudo pacman -Fy
```

## Package Cache

Cached packages are usually stored in:

```text
/var/cache/pacman/pkg/
```

Remove old cached versions with `paccache` if `pacman-contrib` is installed:

```sh
sudo paccache -r
```

## Explicit Packages

```sh
pacman -Qe
```

List explicitly installed native packages:

```sh
pacman -Qen
```

## Foreign Packages

```sh
pacman -Qm
```

Useful for finding packages that are not currently present in configured repositories, including many AUR-installed packages.

## Download Without Installing

```sh
sudo pacman -Sw package
```

## Upgrade a Local Package

```sh
sudo pacman -U package.pkg.tar.zst
```

## Important

On Arch-based systems, avoid doing repository database refreshes followed by selective package upgrades.

Prefer:

```sh
sudo pacman -Syu
```

for normal system upgrades.
