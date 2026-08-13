# Zsh Cheatsheet ⚡

Quick commands, configuration snippets, aliases, functions, and prompt setup for Zsh.

## Config

Main interactive configuration:

```text
~/.zshrc
```

Open it:

```zsh
$EDITOR ~/.zshrc
```

Reload:

```zsh
source ~/.zshrc
```

Or replace the current shell:

```zsh
exec zsh
```

## Variables

```zsh
name="Nihit"
echo "$name"
```

Export:

```zsh
export EDITOR=nvim
```

## Aliases

```zsh
alias ll='eza -lah --icons --git'
alias grep='rg'
alias cat='bat'
```

List aliases:

```zsh
alias
```

Remove one:

```zsh
unalias ll
```

## Functions

```zsh
hello() {
    echo "hello from zsh ⚡"
}
```

Arguments:

```zsh
greet() {
    echo "hello $1"
}
```

## Command Substitution

```zsh
echo "$(pwd)"
```

Example:

```zsh
cd "$(fd -t d | fzf)"
```

## History

Useful `.zshrc` settings:

```zsh
HISTFILE="$HOME/.zsh_history"
HISTSIZE=10000
SAVEHIST=10000

setopt HIST_IGNORE_DUPS
setopt SHARE_HISTORY
```

## Completion

Enable Zsh completion:

```zsh
autoload -Uz compinit
compinit
```

## Oh My Zsh

Typical location:

```text
~/.oh-my-zsh
```

Typical `.zshrc` setup:

```zsh
export ZSH="$HOME/.oh-my-zsh"

plugins=(
    git
)

source "$ZSH/oh-my-zsh.sh"
```

## Starship

Initialize Starship:

```zsh
eval "$(starship init zsh)"
```

Use a shell-specific config:

```zsh
export STARSHIP_CONFIG="$HOME/.config/starship-zsh.toml"
eval "$(starship init zsh)"
```

Example character:

```toml
[character]
success_symbol = '[╰─❯](bold green)'
error_symbol = '[╰─❯](bold red)'
vimcmd_symbol = '[╰─❯](bold yellow)'
```

## Powerlevel10k

Typical configuration:

```text
~/.p10k.zsh
```

Configure:

```zsh
p10k configure
```

Reload:

```zsh
source ~/.p10k.zsh
```

## Startup Benchmark

```zsh
time zsh -i -c exit
```

Run it several times rather than judging startup speed from one measurement.

## Useful

```zsh
type command
which command
whence command
alias
functions
setopt
```

## Change Login Shell

```sh
chsh -s "$(which zsh)"
```

Verify the configured login shell:

```sh
getent passwd "$USER" | cut -d: -f7
```

## Emergency Fish Portal 🐟

Because sometimes you remember where home is.

```zsh
heart() {
    echo "♥ → returning home... 🐟"
    exec fish
}
```

Then:

```zsh
heart
```
