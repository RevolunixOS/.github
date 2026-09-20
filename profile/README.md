# RevolunixOS

RevolunixOS preserves a complete NixOS environment focused on declarative virtualization, reusable system configuration, custom package integration, and a Hyprland workstation setup. It was used as a daily workstation throughout a three-year BTS program.

The repositories are archived and read-only. They remain available as technical documentation and source examples.

## Featured work

| Repository | What it contains |
| --- | --- |
| [`module-virtual-machines`](https://github.com/RevolunixOS/module-virtual-machines) | A declarative VFIO/libvirt module that generates host configuration, virtual-machine definitions, PCI lifecycle hooks, storage, firmware settings, and guest-specific behavior from Nix options. |
| [`module-system`](https://github.com/RevolunixOS/module-system) | Reusable NixOS and Home Manager configuration fragments, separated into command-line and graphical environments. |
| [`revolunixpkgs`](https://github.com/RevolunixOS/revolunixpkgs) | The package and module entry point used to expose RevolunixOS utilities and configuration components. |
| [`dotfiles`](https://github.com/RevolunixOS/dotfiles) | A complete workstation configuration showing how the packages and modules were composed in a real NixOS installation. |

## Declarative VFIO and libvirt

The virtual-machine module covers the full path between a Nix configuration and a usable accelerated guest:

- PCI devices are described by function, with host and guest addressing kept in the generated configuration.
- Devices can use boot-time VFIO binding or dynamic detach and reattach around a VM session.
- Libvirt hooks handle preparation, startup, release, and host recovery.
- The module generates both the primary guest and a setup-oriented domain where required.
- Storage definitions, qcow2 disks, OVMF firmware, virtual TPM, CPU topology, and Looking Glass integration are generated declaratively.
- GPU workflows include option-ROM handling and configurable Resizable BAR operations through sysfs.
- Separate profiles adapt the generated domain for Windows, Linux, and macOS guests.

The repository README documents the option model, generated resources, lifecycle, and current hardware assumptions in detail.

## NixOS structure and desktop tooling

The rest of the organization demonstrates a modular workstation design:

- system-level and Home Manager configuration are split into reusable CLI and graphical components;
- the reference configuration integrates Hyprland, Waybar, Rofi, terminal tooling, theming, and workstation services;
- focused packages provide Rofi menus, Wayland helpers, VM launchers, backup tooling, IDE integration, and other desktop utilities;
- the package set exposes these components through a common flake interface.

## Archive status

This organization is now a read-only archive because its development period has ended, not because the environment was left unfinished. Most repositories reflect their original NixOS 24.05-era environment and the hardware assumptions documented in each project. The code is kept public to show the implementation, design choices, and integration work; it is no longer maintained against current NixOS releases.
