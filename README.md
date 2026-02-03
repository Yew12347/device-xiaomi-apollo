# device-xiaomi-apollo

Trying to port **mainline Linux** and **postmarketOS** to the **Xiaomi Mi 10T / Redmi K30S Ultra / Mi 10T Pro (codename: apollo)**.

This repository contains the device support for pmOS (PostmarketOS) and Linux for the apollo platform — including kernel device info and a base DTS from the Android vendor DTB.

---

## 📌 Project Status

**⚠️ Work In Progress**

This port is not complete — the device may not boot fully yet.  
Some subsystems may be missing, especially display, audio, sensors, and modem support, while the core kernel runs or attempts to boot.

Status highlights:

- Mainline kernel build included
- base DTS from Android DTB provided
- postmarketOS target i-phoshootloader unlock required (Xiaomi bootloader requires a countdown timer before unlock)

> This port is experimental — please do not expect a fully working phone yet.  
> Progress may be slow due to vendor restrictions and lack of upstream drivers.

---

## 📁 Repository Contents

| File/Folder | Purpose |
|-------------|---------|
| `APKBUILD` | pmOS package build config |
| `deviceinfo` | Device metadata for pmOS |
| `modules-initfs` | Modules for initial ramfs environment |
| `sm8250-xiaomi-apollo.dtb` | Device tree blob from Android (reference only) |

---

## 🛠 Building

This device tree is intended to be used with the `pmbootstrap` build system from postmarketOS.

Basic steps (pmOS build environment must be set up):

```sh
pmbootstrap init
pmbootstrap install --android-recovery-zip
pmbootstrap export
cd $(dirname $(readlink /tmp/postmarketOS-export/pmos-*.zip))

---

## Note
this readme is ai generated because i dont know how to phrase it
