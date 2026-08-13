# eza Cheatsheet

`eza` is a modern replacement for `ls`.

## Basic

```sh
eza
```

## Long View

```sh
eza -l
```

## Hidden Files

```sh
eza -a
```

## Long + Hidden

```sh
eza -la
```

## Icons

```sh
eza --icons
```

## Tree

Who needs `tree`? 😭

```sh
eza --tree
```

Limit depth:

```sh
eza --tree --level=2
```

## Git Status

```sh
eza -l --git
```

## Directories First

```sh
eza --group-directories-first
```

## Human-Friendly Combo

```sh
eza -lah \
  --icons \
  --git \
  --group-directories-first
```

## Tree Combo

```sh
eza --tree \
  --icons \
  --git \
  --level=3
```

## Aliases

### Zsh / Bash

```sh
alias ls='eza --icons'
alias ll='eza -lah --icons --git --group-directories-first'
alias tree='eza --tree --icons'
```

### Fish

```fish
alias ls 'eza --icons'
alias ll 'eza -lah --icons --git --group-directories-first'
alias tree 'eza --tree --icons'
```
