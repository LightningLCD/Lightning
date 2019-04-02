
Debian
====================
This directory contains files used to package lightningd/lightning-qt
for Debian-based Linux systems. If you compile lightningd/lightning-qt yourself, there are some useful files here.

## lightning: URI support ##


lightning-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install lightning-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your lightningqt binary to `/usr/bin`
and the `../../share/pixmaps/lightning128.png` to `/usr/share/pixmaps`

lightning-qt.protocol (KDE)

