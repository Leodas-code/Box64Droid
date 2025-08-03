# **Box64Droid Enhanced**

[![Typing SVG](https://readme-typing-svg.demolab.com/?lines=Welcome+to+Box64Droid;The+Fastest+Windows+Emulator)](https://git.io/typing-svg)

Box64Droid is a versatile toolkit of scripts designed to automate the installation of preconfigured rootfs with **Box64**, **Box86**, **Wine**, **DXVK**, **D8VK** on Android devices. It originated as a fork of Box4Droid (with Box64) and has evolved into a powerful emulator environment.

---

## 📢 News and Updates

[![telegram](https://img.shields.io/badge/chat-telegram-brightgreen.svg?logo=telegram&style=flat-square)](https://t.me/x86_64_on_android)
[![discord](https://img.shields.io/discord/308323056592486420?logo=discord)](https://discord.gg/thjpZ4P7Bm)

Box64Droid is a project with scripts that automate installing preconfigured rootfs with [Box64](https://github.com/ptitSeb/box64), [Box86](https://github.com/ptitSeb/box86), [Wine](https://github.com/Kron4ek/Wine-Builds), [DXVK](https://github.com/doitsujin/dxvk), [D8VK](https://github.com/AlpyneDreams/d8vk) on Android. Originally was a [fork](https://github.com/Ilya114/Box4Droid) of [Box4Droid](https://github.com/Herick75/Box4Droid) with Box64.

- News about the project are published on the [Telegram](https://t.me/box64droidch) channel.
- The project site is available [here](https://ilya114.github.io).

---

## 📦 Installation Instructions

1. **Install the required apps:**
   - `Termux`
   - `Termux-x11`
   - `Termux:Widget`

2. **Run the installer:**

   ```bash
   curl -o install https://raw.githubusercontent.com/Leodas-code/Box64Droid/v2.0/installers/install.sh && chmod +x install && ./install
   
   ```

   - Select your desired version (recommend: `native`)
   - Wait for the full installation to complete.

3. **Launch Box64Droid:**

   ```bash
   box64droid --start
   ```

   This will start Termux-X11 and launch the start menu.

4. **Use Input Bridge (for input handling):**
   - Install APK
   - Launch the app both on Android and from Wine inside Box64Droid.

---

## 🏠 Homescreen Launch (Native Version)

- Use **Termux:Widget** to:
  - Launch Box64Droid
  - Check for updates
  - Open Wine or other GUI options

---

## 📋 System Requirements

- **GPU:** Adreno 610+ (VirGL supports others, but compatibility may vary)
- **Android:**
  - 12+ (non-root, VirGL version)
  - 10+ (root version)
  - 9+ (native version)
- **Architecture:** 64-bit Android
- **Storage Space:**
  - ~4.2 GB for root version
  - ~4.5 GB for non-root version
  - ~3.3 GB for VirGL version

🔧 _For best performance and stability, use the root or native version._

---

## ⚙️ Configuration

After first launch, Box64Droid creates config files in `/sdcard/Box64Droid/`:

- `Box64Droid.conf` – configures Box64, Box86, Wine, and rootfs settings.
- `DXVK_D8VK.conf` – for setting DXVK-related environment variables.
- `DXVK_D8VK_HUD.conf` – for DXVK_HUD configurations.

👉 You can add as many environment variables as needed.

---

## 🐛 Known Issues

- **Fast install failure:** Caused by Termux update process breaking mid-way. ➜ _Clear Termux data_ to resolve.
- **Android 12+ kill signal:** You may see `[Process completed (signal 9)]`. Fix it via ADB:

  ```bash
  adb shell "/system/bin/device_config put activity_manager max_phantom_processes 2147483647"
  ```

- **Winetricks slow when Proton installed** (non-root version).
  
---

## 💾 Mounting SD Card / External HDD or SSD (Chroot Version Only)

1. **Locate the mount point:**
   - SD cards: `/storage/XXXX-XXXX`
   - External drives: `/mnt/media_rw/XXXXXXXXXXXXXXX`

2. **Bind into chroot:**
   - Edit `$PREFIX/bin/box64droid`
   - Add this before the `sudo chroot login ...` line:

     ```bash
     sudo mount --bind /mnt/media_rw/drivename $ROOTFSPATH/needfolder
     ```

   - Ensure `needfolder` exists in `~/ubuntu`:

     ```bash
     sudo mkdir ~/ubuntu/needfolder
     ```

---

## 🧰 Software & Licenses Used

| Component              | License                   |
|------------------------|---------------------------|
| Termux-app             | GPLv3                     |
| Box64 by ptitseb       | MIT                      |
| Box86 by ptitseb       | MIT                      |
| Wine variants          | GPL-2.1 / MIT / Valve     |
| Mesa                   | MIT, Khronos, SGI, Boost  |
| Termux-x11             | GPL-3.0                   |
| DXVK                   | Zlib                      |
| D8VK                   | Zlib                      |
| DXVK-Async             | Zlib                      |
| DXVK-GPLAsync          | GPL                       |
| WineD3D for Windows    | GPL-2.0+                  |
| Winetricks             | GPL                       |
| vkd3d-proton           | LGPL v2.1                 |
| glibc-prefix           | MIT                       |
| proot-distro           | GPL-3.0                   |

---

## Credits

- **llya114** - Original Developer of Box64Droid

---
