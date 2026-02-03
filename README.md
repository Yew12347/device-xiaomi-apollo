# device-xiaomi-apollo

Trying to port **mainline Linux** and **postmarketOS** to the  
**Xiaomi Mi 10T / Redmi K30S Ultra / Mi 10T Pro** (codename: **apollo**).

This repository contains device support files for postmarketOS (pmOS) and
mainline Linux, including device info and a base DTS extracted from the
Android vendor DTB.

---

## Note
this readme is ai generated with a little big of modification by me because i dont know hwo to phrase it

---

## 📌 Project Status

**⚠️ Work in Progress**

This port is incomplete and may not boot or may only partially boot.

Several subsystems are still missing or non-functional, including but not
limited to:

- Display
- Audio
- Sensors
- Modem / cellular

The kernel may boot or attempt to boot, but the system is **not usable yet**.

### Current highlights

- Mainline kernel support in progress
- Base DTS extracted from Android DTB
- postmarketOS device target created
- Bootloader unlock required  
  (Xiaomi enforces a countdown timer before unlocking)

> This port is experimental.  
> Do **not** expect a fully working phone.
>
> Development is slowed by vendor restrictions and missing upstream drivers.

---

## 📁 Repository Contents

| File / Folder | Purpose |
|---------------|---------|
| `APKBUILD` | pmOS package build configuration |
| `deviceinfo` | Device metadata for postmarketOS |
| `modules-initfs` | Kernel modules included in initramfs |
| `sm8250-xiaomi-apollo.dtb` | DTB extracted from Android Image (temporary i think) |

---

## 🛠 Building

This device tree is intended for use with **pmbootstrap**.

You must already have a working postmarketOS build environment.

Basic steps:

```sh
pmbootstrap init
pmbootstrap install --android-recovery-zip
pmbootstrap export
cd $(dirname $(readlink /tmp/postmarketOS-export/pmos-*.zip))
```
