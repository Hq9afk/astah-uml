# astah-uml

Arch Linux PKGBUILD for [Astah UML](https://astah.net/) 11.0.0. Unofficial, local use only.

## Prerequisites

```bash
sudo pacman -S --needed base-devel jre-openjdk unzip
```

## Install

```bash
git clone https://github.com/hq9afk/astah-uml.git
cd astah-uml
makepkg -si
```

The `-nojvchk` flag is passed automatically to bypass Astah's Java version check.
