# 📱 Install LineageOS 20 on Redmi Note 7 (lavender)

This guide will walk you through unlocking the bootloader, flashing a custom recovery, and installing LineageOS 20 (Android 13) on the Redmi Note 7 (lavender).

> ⚠️ DISCLAIMER: This process may void your warranty and may brick your device if done improperly. Proceed at your own risk.

## 🔧 Steps Overview

1. [Requirements](#-requirements)
2. [Unlock Bootloader](#-unlock-bootloader)
3. [Install Lineage Recovery](#-install-lineage-recovery)
4. [Install LineageOS 20](#-install-lineageos-20)
5. [Troubleshooting Help](#-troubleshooting)
6. [Useful Links](#-helpful-links)

---

## 📋 Requirements

* Xiaomi Redmi Note 7 (Code name: lavender)
* USB Cable
* Computer (Windows/Linux/macOS)
* USB Drivers (for ADB/Fastboot)
* Backup all your data (this process wipes everything)

### Software to Install

* [Android SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools)
* [Lineage Recovery](https://download.lineageos.org/devices/lavender/install)
* [LineageOS 20 ROM](https://download.lineageos.org/lavender)
* \[GApps (optional)]\([https://opengapps.org/](https://opengapps.org/) or [https://nikgapps.com/](https://nikgapps.com/))

> 📁 The required `recovery.img` and `lineage-20-*.zip` files have been added to this repository for your convenience.

---

## 🔓 Unlock Bootloader

1. Enable Developer Options:

   * Go to Settings → About phone → Tap "MIUI version" 7 times.

2. Enable OEM Unlock and USB Debugging:

   * Settings → Additional settings → Developer options
   * Enable **OEM unlocking** and **USB debugging**

3. Log in to Mi Account.

4. Boot to fastboot mode:

   * Power off the phone
   * Hold **Volume Down + Power**

5. Use Mi Unlock Tool (Windows only):

   * [Download Mi Unlock Tool](https://en.miui.com/unlock/)
   * Connect the phone, log in, and unlock the bootloader.

> 🔄 Wait 7 days if Xiaomi imposes the delay. Retry after that.

---

## 🔁 Install Lineage Recovery

1. Download `recovery.img` from the [LineageOS lavender install page](https://download.lineageos.org/devices/lavender/install) or use the file included in this repository.
2. Boot into fastboot mode:

   * Power off the device
   * Hold **Volume Down + Power**
3. Connect your phone to PC via USB.
4. Flash the recovery image:

```bash
fastboot flash recovery recovery.img
```

5. Reboot to recovery:

```bash
fastboot reboot recovery
```

---

## 📲 Install LineageOS 20

1. Reboot into Lineage Recovery.
2. Select "Factory Reset" → Format data / factory reset.
3. Go back → Apply Update → Apply from ADB.
4. On PC, sideload the LineageOS ROM:

```bash
adb sideload lineage-20-*.zip
```

> ✅ You can also use the included LineageOS ZIP file in this repo if you don't want to download it separately.

5. (Optional) Sideload GApps the same way if required.
6. After flashing, return to main menu → Reboot → System.

---

## 🆘 Troubleshooting

* **Bootloop?** → Reboot to recovery, factory reset, re-flash
* **ADB not detecting device?** → Ensure drivers and permissions are correct
* **Installation fails?** → Check SHA of ROM zip, retry sideload

---

## 🔗 Helpful Links

* [Official LineageOS Wiki](https://wiki.lineageos.org/)
* [LineageOS ROM for Lavender](https://download.lineageos.org/lavender)
* [Lavender Install Instructions](https://wiki.lineageos.org/devices/lavender/install)
* [Mi Unlock Tool](https://en.miui.com/unlock/)
* [OpenGApps](https://opengapps.org/)
* [ADB/Fastboot Tools](https://developer.android.com/studio/releases/platform-tools)
