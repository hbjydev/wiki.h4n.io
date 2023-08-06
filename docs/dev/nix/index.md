# Nix

Nix is three things (referred to as the "Nix Trinity"):

1. A package manager
2. An operating system (NixOS)
3. A functional, declarative language

It's useful for providing
[hermetic builds](https://sre.google/sre-book/release-engineering/) for
applications, as well as bootstrapping development environments with Flakes, or
managing your _whole_ environment using tools like
[home-manager](https://github.com/nix-community/home-manager) and
[nix-darwin](https://github.com/lnl7/nix-darwin).
