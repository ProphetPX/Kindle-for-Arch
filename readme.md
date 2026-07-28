# Kindle App for Arch Linux

A simple Kindle desktop app for Arch Linux based on Electron JS. It wraps Amazon's cloud reader in a secure desktop frame.

## Prerequisites

Before building, make sure your system has the standard base-devel tools installed:

```bash
sudo pacman -S base-devel
```

## Installation

Since this package features a dedicated Arch `PKGBUILD` script, you can build and install it natively using `makepkg`. 

Open your terminal inside this repository directory and run:

```bash
makepkg -si
```

This will automatically check for dependencies, build the local packages, and install the `kindle-for-arch` utility system-wide.

## Running the App

Once installed, you can launch the application directly from your system's applications menu, or by running this command in your terminal:

```bash
kindle
```
