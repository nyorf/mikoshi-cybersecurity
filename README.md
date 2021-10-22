# Mikoshi Cybersecurity Repository

## What is this?

This is a custom repository (currently being set up and filled with packages, not yet ready to use), maintained by @nyorf

This repository includes (or, at least, will include) all (most of) Kali Linux' packages for your Arch system.

Everything is currently packaged by me (@nyorf), so you can look through my PKGBUILDs [here](https://github.com/nyorf/PKGBUILDs), I'm not hiding anything :D

## Install repository to your Arch Linux (or any Arch-based) distro

I will write a one-click install script eventually, but for now — here's how you can add this repository to your pacman package manager:

**import key to pacman's GPG trust.db**

    sudo pacman-key --recv-keys 3E57BAFEADD3EAC60D893CB6ECDA8403636A3FEB

**check if the key was actually added**

    sudo pacman-key --finger 3E57BAFEADD3EAC60D893CB6ECDA8403636A3FEB

**sign the key locally**

    sudo pacman-key --lsign-key 3E57BAFEADD3EAC60D893CB6ECDA8403636A3FEB

**install mirrorlist pkg**

    curl -O https://raw.githubusercontent.com/nyorf/mikoshi-cybersecurity/master/x86_64/mikoshi-mirrorlist-2021.10.20-3-x86_64.pkg.tar.zst && sudo pacman -U mikoshi-mirrorlist-2021.10.20-3-x86_64.pkg.tar.zst

**edit /etc/pacman.conf — add these lines after your last repository entry**

    [mikoshi-cybersecurity]
    SigLevel = Required DatabaseOptional
    Include = /etc/pacman.d/mikoshi-mirrorlist

**sync everything**

    sudo pacman -Syyu

**install mikoshi-keyring**

    sudo pacman -S mikoshi-keyring

## Post-install TODOs

**list all of the available tools**

    sudo pacman -Sgg | grep mikoshi | cut -d' ' -f2 | sort -u

**install all of the tools**

    sudo pacman -S mikoshi

**install a category of tools**

    sudo pacman -S mikoshi-<category>

**see all of mikoshi's categories**

    sudo pacman -Sg | grep mikoshi

