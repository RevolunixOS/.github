# RevolunixOS

RevolunixOS is an experimental NixOS ecosystem for building a reproducible
desktop, packaging small workstation utilities, and managing local virtual
machines declaratively.

The organization currently contains a development snapshot rather than a
finished distribution. Most projects were created around NixOS 24.05 and a
Hyprland-based personal workstation, so review their assumptions before using
them on another machine.

## Start here

| Project | Purpose |
| --- | --- |
| [`revolunixpkgs`](https://github.com/RevolunixOS/revolunixpkgs) | Custom Nixpkgs package set for RevolunixOS utilities |
| [`module-system`](https://github.com/RevolunixOS/module-system) | Reusable CLI and graphical NixOS/Home Manager configuration fragments |
| [`module-virtual-machines`](https://github.com/RevolunixOS/module-virtual-machines) | Declarative libvirt VMs, Looking Glass, and optional PCI passthrough |
| [`dotfiles`](https://github.com/RevolunixOS/dotfiles) | Reference workstation configuration for the original development host |
| [`DevelopementEnvironement`](https://github.com/RevolunixOS/DevelopementEnvironement) | Superproject that pins the ecosystem repositories as submodules |
| [`revolui`](https://github.com/RevolunixOS/revolui) | Early Nuxt proof of concept for an infrastructure dashboard |

## Desktop utilities

The `pkg-*` repositories package focused tools such as Rofi menus, screenshot
helpers, a Neovim launcher, a Citra AppImage wrapper, and small Wayland
utilities. They can also be consumed together through `revolunixpkgs`.

## Project status

These repositories are public development artifacts. Expect old Nixpkgs pins,
legacy references to the former `RevoluNix` namespace, and configuration tied
to the original author's workstation. Test changes in a VM or disposable NixOS
generation before deploying them to a daily-use system.

Contributions that improve portability, documentation, or reproducibility are
welcome through issues and pull requests in the relevant repository.
