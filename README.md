# mikoshi-cybersecurity

barebones installation guide (TBC):

import key to pacman's GPG trust.db: sudo pacman-key --recv-keys 27F15AF7A5D8BD074B88EC1078F62A59070BA3FE

check if the key was actually added: sudo pacman-key --finger 27F15AF7A5D8BD074B88EC1078F62A59070BA3FE

sign the key: sudo pacman-key --lsign-key 27F15AF7A5D8BD074B88EC1078F62A59070BA3FE

install mirrorlist pkg:
    curl -O https://raw.githubusercontent.com/nyorf/mikoshi-cybersecurity/master/x86_64/mikoshi-mirrorlist-2021.10.20-1-x86_64.pkg.tar.zst
    sudo pacman -S mirrorlist-2021.10.20-1-x86_64.pkg.tar.zst

edit /etc/pacman.conf:
add these lines after your last repo entry:
[mikoshi-cybersecurity]
SigLevel = Required DatabaseOptional
Include = /etc/pacman.d/mikoshi-mirrorlist

sync everything: sudo pacman -Syyu

install mikoshi-keyring: sudo pacman -S mikoshi-keyring
