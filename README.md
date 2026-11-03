# OpenCore-EFI-for-NUC8i7HVK
【20261104】Bootable OC EFI that Functional with macOS 26 Tahoe and macOS 15 Sequoia


# Usage for macOS 26 Tahoe
Just plugin the installer and run it! you DON'T need to set ANYTHING

### Notes
1. This EFI supports OTA upgrade in Tahoe, you need to do ***Reset NVRAM*** every time you upgrade to ensure bluetooth works
2. I only guarantee running Sequoia on Release:20250819, newer versions are optimized only for Tahoe
3. Do not change the sequence of Intel Bluetooth kexts, otherwise it won't work
4. SimpleHDA needs ***Keepsyms=1*** to work normally, do not delete it


# Older Version 20250819

### Usage for macOS 15 Sequoia
1. Download 20250819 from Release
1. Rename Config-Sequoia.plist to Config.plist
2. Run macOS installer until finish
3. After installing, using tools like OCAT to generate your SMBIOS
4. Using OCLP-Mod for intel wireless fixing

### Config-Tahoe
* Mostly good for Tahoe, using ***Itlwm*** for wireless, need modifying SSID and password in Info.plist in Itlwm.kext for Wi-Fi Connection
### Config-Tahoe-Installer
* Disable ***WhatEverGreen*** for installing macOS 26 Tahoe
* Disable ***UEFI-APFS-EnableJumpStart*** for FileVault support
* Enable ***apfs_aligned.efi*** in UEFI-Drivers for FileVault support
### Config-Tahoe-FileVault
* Disable ***UEFI-APFS-EnableJumpStart*** for FileVault support
* Enable ***apfs_aligned.efi*** in UEFI-Drivers for FileVault support

# Credits
* [Apple](https://apple.com) for macOS
* [Acidanthera](https://github.com/acidanthera) for OpenCore
* [goodbest](https://github.com/goodbest/Polaris22Fixup) and [Baio1977](https://github.com/Baio1977/Polaris22Fixup) for continuous support on VegaM GPU fixups
* All other kext driver developers
