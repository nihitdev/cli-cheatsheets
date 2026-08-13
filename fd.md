# fd Cheatsheet

`fd` is a fast and friendly alternative to `find`.

## Find

```sh
fd filename
```

## Find Extension

```sh
fd -e rs

fd -e md
```

## Files Only

```sh
fd -t f
```

## Directories Only

```sh
fd -t d
```

## Hidden Files

```sh
fd -H
```

## Include Ignored Files

```sh
fd -I
```

## Exact Path

```sh
fd '^README\.md$'
```

## Execute Command

```sh
fd -e md -x wc -l
```

## Search and Open

```sh
nvim "$(fd -t f | fzf)"
```

## Search Project Files

```sh
fd -t f
```
