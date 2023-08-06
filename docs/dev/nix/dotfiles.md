# Dotfiles

My dotfiles are in my [dots.nix](https://github.com/hbjydev/dots.nix) repository
and are managed by Nix. They largely configure NixOS and nix-darwin, and then
add home-manager on top for shared configuration between them. This means that
my dotfiles are pretty much the same setup across macOS and Linux.

## Setup

To install/set up my dotfiles, you need to follow these steps:

## NixOS

1. Install NixOS
2. As root:
    1. `nix-env -iA git`
    2. `rm -rf /etc/nixos`
    3. `git clone https://github.com/hbjydev/dots.nix.git /etc/nixos`
    4. `sudo chown -R hayden:users /etc/nixos`
    5. `sudo nixos-rebuild switch --flake '/etc/nixos#personal-nixos'`
3. Reload the shell

## macOS/Darwin

1. Install Nix
    - Hello
2. Install `nix-darwin`
    - `cd /tmp`
    - `nix-build https://github.com/LnL7/nix-darwin/archive/master.tar.gz -A installer`
    - `./result/bin/darwin-installer`
    - Select `n` for editing the `configuration.nix`
    - Select `y` for adding the `nix-darwin` channel.
3. Install Homebrew
    - `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
4. Clone the dotfiles repo
    - `nix-shell -p pkgs.git --run 'git clone https://github.com/hbjydev/dots.nix.git ~/.config/nix'`
5. Rebuild with the flake configuration
    - `darwin-rebuild switch --flake "$HOME/.config/nix#personal-darwin"`
6. Reload the shell
