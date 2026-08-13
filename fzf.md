# fzf Cheatsheet

`fzf` is a command-line fuzzy finder.

## Basic

```sh
fzf
```

## Find File

```sh
fd -t f | fzf
```

## Open File

```sh
nvim "$(fd -t f | fzf)"
```

## Search Git Files

```sh
git ls-files | fzf
```

## Choose Git Branch

```sh
git branch --format='%(refname:short)' | fzf
```

## Preview Files

With `bat`:

```sh
fzf --preview 'bat --color=always --style=numbers {}'
```

With `eza` for directories:

```sh
fd -t d | fzf --preview 'eza --tree --level=2 {}'
```

## Multiple Selection

```sh
fzf --multi
```

## Reverse Layout

```sh
fzf --layout=reverse
```

## Height

```sh
fzf --height=40%
```

## Useful Combo

```sh
fd -t f |
  fzf --preview 'bat --color=always --style=numbers {}'
```
