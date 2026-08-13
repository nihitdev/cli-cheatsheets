# ripgrep Cheatsheet

`ripgrep` (`rg`) is a fast recursive search tool.

## Search

```sh
rg "hello"
```

## Ignore Case

```sh
rg -i "hello"
```

## Exact Word

```sh
rg -w "hello"
```

## Show Line Numbers

```sh
rg -n "hello"
```

## Search Specific File Type

```sh
rg "TODO" -t rust

rg "TODO" -t js
```

## Search Glob

```sh
rg "hello" -g "*.toml"

rg "hello" -g "*.md"
```

## Exclude

```sh
rg "hello" -g '!node_modules/**'
```

## Hidden Files

```sh
rg --hidden "hello"
```

## Include Ignored Files

```sh
rg --no-ignore "hello"
```

## Files Containing Match

```sh
rg -l "hello"
```

## Files Without Match

```sh
rg -L "hello"
```

## Count Matches

```sh
rg -c "hello"
```

## List Files

```sh
rg --files
```

Combine with `fzf`:

```sh
rg --files | fzf
```
