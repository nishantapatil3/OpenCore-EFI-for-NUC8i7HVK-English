# OpenCore-EFI-for-NUC8i7HVK
Bootable OC EFI that Functional with macOS 26 Tahoe and macOS 15 Sequoia

---

## Usage for macOS 26 Tahoe
Just plugin the installer and run it! you DON'T need OCLP，don't need to set ANYTHING

### Notes
1. This EFI supports OTA upgrade in Tahoe, you need to do ***Reset NVRAM*** every time you upgrade to ensure bluetooth works
2. I only guarantee running Sequoia on Release:20250819, newer versions are optimized only for Tahoe
3. Do not change the sequence of Intel Bluetooth kexts, otherwise it won't work
4. SimpleHDA needs ***Keepsyms=1*** to work normally, do not delete it
5. VDA Hardware Decode only works when enables HD630 Graphics, DRM are still not working
6. Supports FileVault, but not recommended to use

## Older Version 20250819

### Usage for macOS 15 Sequoia
1. Download 20250819 from Release
1. Rename Config-Sequoia.plist to Config.plist
2. Run macOS installer until finish
3. After installing, using tools like OCAT to generate your SMBIOS
4. Using OCLP-Mod for intel wireless fixing

### Config-Tahoe
* Mostly good for Tahoe, using ***Itlwm*** for wireless, need modifying SSID and password in Info.plist in Itlwm.kext for Wi-Fi Connection
### Config-Tahoe-Installer
* Disable ***WhateverGreen*** for installing macOS 26 Tahoe
* Disable ***UEFI-APFS-EnableJumpStart*** for FileVault support
* Enable ***apfs_aligned.efi*** in UEFI-Drivers for FileVault support
### Config-Tahoe-FileVault
* Disable ***UEFI-APFS-EnableJumpStart*** for FileVault support
* Enable ***apfs_aligned.efi*** in UEFI-Drivers for FileVault support

## Credits
* [Apple](https://apple.com) for macOS
* [Acidanthera](https://github.com/acidanthera) for OpenCore
* [Baio1977](https://github.com/Baio1977/Polaris22Fixup) for continuous support on VegaM GPU fixups
* All other kext driver developers

---


## 使用方法（macOS 26 Tahoe）

插上安装盘直接启动即可，不需要 OCLP，也不需要做任何设置

### 注意事项

1. 本 EFI 支持在 Tahoe 下进行 OTA 升级；每次升级后都需要执行 ***Reset NVRAM（重置 NVRAM）***，以保证蓝牙正常工作
2. 仅保证 Sequoia 在 Release:20250819 版本上正常使用；更新的版本只针对 Tahoe 做了优化
3. 不要改动 Intel 蓝牙相关 kext 的排列顺序，否则会失效
4. SimpleHDA 需要 ***Keepsyms=1*** 才能正常工作，请勿删除
5. VDA 硬件解码仅在启用 HD630 核显时生效，DRM 目前仍不可用
6. 支持Apple FileVault，但不建议启用

## 旧版本 20250819

### 使用方法（macOS 15 Sequoia）

1. 从 Release 页面下载 20250819
2. 将 Config-Sequoia.plist 重命名为 Config.plist
3. 运行 macOS 安装程序，直至安装完成
4. 安装完成后，使用 OCAT 等工具生成 SMBIOS
5. 使用 OCLP-Mod 修复 Intel 无线网卡

### Config-Tahoe

* 在 Tahoe 下大体可用，无线使用 ***Itlwm***；需要先在 Itlwm.kext 的 Info.plist 中修改 SSID 与密码，才能连接 Wi-Fi

### Config-Tahoe-Installer

* 安装 macOS 26 Tahoe 时需禁用 ***WhateverGreen***
* 为支持 FileVault，需禁用 ***UEFI-APFS-EnableJumpStart***
* 为支持 FileVault，需在 UEFI-Drivers 中启用 ***apfs_aligned.efi***

### Config-Tahoe-FileVault

* 为支持 FileVault，需禁用 ***UEFI-APFS-EnableJumpStart***
* 为支持 FileVault，需在 UEFI-Drivers 中启用 ***apfs_aligned.efi***

## 致谢

* [Apple](https://apple.com) —— 提供 macOS
* [Acidanthera](https://github.com/acidanthera) —— 提供 OpenCore
* [Baio1977](https://github.com/Baio1977/Polaris22Fixup) —— 对 VegaM GPU的持续修复和支持
* 以及其他所有 kext 与驱动开发者

---