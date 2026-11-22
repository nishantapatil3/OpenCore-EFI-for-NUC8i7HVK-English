# OpenCore-EFI-for-NUC8i7HVK — US English

This fork sets the installer language and keyboard to US English for the Intel NUC8i7HVK. OpenCore clears the previous firmware value for `prev-lang:kbd` and sets it to `en-US:0` at each boot.

To update an installer USB that already uses the same upstream EFI revision (`d516d3d`), replace `EFI/OC/config.plist` on its EFI System Partition with the file from this fork. Eject the USB and boot from it again. The installer volume can be reused. The configuration has passed plist validation. An English-language boot on hardware is pending verification.

[Original EFI and maintainer notes](https://github.com/ZEQ-Avidia/OpenCore-EFI-for-NUC8i7HVK)
Bootable OC EFI that Functional with macOS 26 Tahoe and macOS 15 Sequoia

---

## Notes about this EFI
1. This EFI supports OTA upgrade in Tahoe, you need to do ***Reset NVRAM*** every time you upgrade to ensure bluetooth works normally
2. Do not change the sequence of Intel Bluetooth kexts, otherwise it won't work
3. SimpleHDA needs ***Keepsyms=1*** to work normally, do not delete it
4. VDA and DRM are working normally, already using ***-radcodec*** for Vega M to support hardware accelerate
5. Supports FileVault by using Apple's ***"apfs_aligned.efi, Sequoia version"***, using modded no log version for cleaner boot screen. If you want to use the formal  way in OpenCore, change it to ***False*** and enable ***Jumpstart***

## Usage for macOS 26 Tahoe
Just plugin the installer and run it! you don't need OCLP, don't need to set ANYTHING, just ***Reset NVRAM*** after finishing install to make bluetooth work.

## Usage for macOS 15 Sequoia
I dont want to have two versions of ***AirportItlwm*** in one config, so before or after installing Sequoia, follow **[laobamac](https://github.com/laobamac/itlwm)**'s modified Itlwm project, Download the Sequoia version of ***AirportItlwm*** and replace into my EFI, then do the install.

## Credits
* [Apple](https://apple.com) for macOS
* [Acidanthera](https://github.com/acidanthera) for OpenCore
* [Baio1977](https://github.com/Baio1977/Polaris22Fixup) for continuous support on VegaM GPU fixups
* [laobamac](https://github.com/laobamac) for works to get rid of OCLP
* All other kext driver developers

---


## 关于本 EFI 的注意事项

1. 本 EFI 支持在 Tahoe 下进行 OTA 升级。每次升级后都需要执行 ***Reset NVRAM（重置 NVRAM）***，以保证蓝牙正常工作
2. 不要改动 Intel 蓝牙相关 kext 的排列顺序，否则会失效
3. SimpleHDA 需要 ***Keepsyms=1*** 才能正常工作，请勿删除
4. VDA 与 DRM 均可正常工作；已为 Vega M 启用 ***-radcodec*** 以支持硬件加速
5. 通过 Apple 的 ***apfs_aligned.efi（Sequoia 版本）*** 支持 FileVault，使用的是我修改的无日志版本，开机画面更干净。如果想用OpenCore官方的方式，请将其改为 ***False*** 并启用 ***Jumpstart***

## 使用方法（macOS 26 Tahoe）

插上安装盘直接启动即可，不需要 OCLP，也不需要做任何设置，只需要在安装好之后按空格重置一遍NVRAM让蓝牙工作。

## 使用方法（macOS 15 Sequoia）

我不想在同一个 config 里放两个版本的 ***AirportItlwm***，因此在安装 Sequoia 之前或之后，请前往 **[laobamac](https://github.com/laobamac/itlwm)** 的修改版 Itlwm 项目，下载适用于 Sequoia 的 ***AirportItlwm*** 并替换进 EFI 再进行安装。

## 致谢

* [Apple](https://apple.com) —— 提供 macOS
* [Acidanthera](https://github.com/acidanthera) —— 提供 OpenCore
* [Baio1977](https://github.com/Baio1977/Polaris22Fixup) —— 对 VegaM GPU 的持续修复与支持
* [laobamac](https://github.com/laobamac) —— 为摆脱 OCLP 所做的工作
* 其他所有 kext 驱动开发者

---