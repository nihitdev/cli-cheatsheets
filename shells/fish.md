# Fish Cheatsheet 🐟

Quick commands and configuration snippets for the Friendly Interactive Shell.

## Config

```text
~/.config/fish/config.fish
```

Open it:

```fish
$EDITOR ~/.config/fish/config.fish
```

Reload:

```fish
source ~/.config/fish/config.fish
```

Or replace the current shell:

```fish
exec fish
```

## Variables

```fish
set name "Nihit"
echo $name
```

Universal variable:

```fish
set -U EDITOR nvim
```

Export:

```fish
set -gx EDITOR nvim
```

Erase:

```fish
set -e name
```

## PATH

```fish
fish_add_path ~/.local/bin
```

## Aliases

```fish
alias ll 'eza -lah --icons --git'
alias grep 'rg'
alias cat 'bat'
```

Persist an alias as a function:

```fish
funcsave ll
```

## Functions

```fish
function hello
    echo "hello from fish 🐟"
end
```

Save it:

```fish
funcsave hello
```

Functions normally live under:

```text
~/.config/fish/functions/
```

## Abbreviations

```fish
abbr -a g git
abbr -a gst 'git status'
abbr -a gc 'git commit'
```

List:

```fish
abbr --show
```

Erase:

```fish
abbr -e gst
```

## Command Substitution

```fish
echo (pwd)
```

Example:

```fish
cd (fd -t d | fzf)
```

## Conditionals

```fish
if test -f README.md
    echo "README exists"
end
```

## Loops

```fish
for file in *.md
    echo $file
end
```

## History

```fish
history
history search git
history delete --exact "command"
```

## Key Bindings

```fish
fish_default_key_bindings
```

Vi mode:

```fish
fish_vi_key_bindings
```

## Fisher

Install plugins with Fisher:

```fish
fisher install owner/plugin
```

List:

```fish
fisher list
```

Update:

```fish
fisher update
```

Remove:

```fish
fisher remove owner/plugin
```

## Debug Startup

```fish
time fish -i -c exit
```

## Useful

```fish
type command
which command
functions
set
status
```

## Change Login Shell

```sh
chsh -s "$(which fish)"
```

Log out and back in for the login-shell change to fully take effect.
