# rtl8812au
Realtek 8812AU driver version 5.2.9

Works fine with Ubuntu 17.04 Zesty 4.10 kernel. Untested on 4.11 & 4.12.
Only support 8812AU.

Source builds with no warnings or errors, and is very stable in use.
Realtek seem to have done a decent job here.

Only changes to vanilla Realtek source added TP-Link VIDs, and slight changes to Makefile for quiet operation.

Added (cosmeticly edited) original Realtek_Changelog.txt, this README.md and dkms.conf.

To build and install module manually:

  make
  sudo make install

To use dkms install:

  (as root, or sudo) copy source folder contents to /usr/src/rtl8812au-5.2.9

  sudo dkms add -m rtl8812au -v 5.2.9
  sudo dkms build -m rtl8812au -v 5.2.9
  sudo dkms install -m rtl8812au -v 5.2.9 

To use dkms uninstall and remove:

  sudo dkms remove -m rtl8812au -v 5.2.9 --all

To install provided Debian/Ubuntu &etc package:

  sudo dpkg -i gord-rtl8812au-dkms_1.0-7_amd64.deb

To uninstall provided Debian/Ubuntu &etc package:

  sudo dpkg -P gord-rtl8812au-dkms

As others have noted, people using NetworkManager need to add this stanza to /etc/NetworkManager/NetworkManager.conf

  [device]
  wifi.scan-rand-mac-address=no
	
