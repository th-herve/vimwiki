# Nix setup

Nix setup on other distro.

## Installation

### Install

```bash
sudo pacman -S nix

```
### use command without sudo

```bash
sudo systemctl enable nix-daemon 
sudo usermod -a -G nix-users $USER  
```

### set up channel

```bash
nix-channel --add https://nixos.org/channels/nixpkgs-unstable
nix-channel --update
```

## Zsh

### Alias to start nix-shell in zsh

```bash
alias nsz="nix-shell --command 'zsh'"
```

### Modify prompt when in a nix-shell

```bash
if [ -n "$IN_NIX_SHELL" ]; then
  export PS1="%F{blue} $PS1"
fi
```
