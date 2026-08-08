# 📡 Meshtastic Heltec V2.1 Automated Nightly Builds

[![GitHub Actions](https://github.com/yo8aiv/meshtastic_heltecv2.1/actions)
[![Latest Release](https://shields.io)](https://github.com)

Automated **Meshtastic firmware** builds compiled every night directly from the official development branch, specifically optimized for the **Heltec WiFi LoRa 32 V2.1** board. Perfect for users tracking cutting-edge updates or utilizing legacy hardware modifications (such as charging and GPS mods).

---

## ⚡ Direct Web Installer (Recommended)

Don't want to mess with command-line tools? Flash your Heltec V2.1 board directly from your Google Chrome or Microsoft Edge browser:

👉 **[Launch the Web Flasher](https://yo8aiv.github.io/web-flash).** 👈

---

## 💾 Manual Downloads

You can obtain the fresh compiled files in two ways:

1. **GitHub Releases (Stable/Latest Checkpoints):** Navigate to the [Releases](https://github.com) section to pick up the most recent pre-packaged release binaries.
2. **GitHub Actions Artifacts (Strictly Nightly):** 
   * Go to the [Actions tab](https://github.com/yo8aiv/meshtastic_heltecv2.1/actions).
   * Click on the top-most successful workflow run.
   * Scroll down to **Artifacts** and download `heltec-v2-firmware`.

### Package Contents
Each download contains:
* `firmware.bin` — For over-the-air (OTA) updates.
* `firmware.factory.bin` — Complete image containing the bootloader, used for fresh USB flashing.

---

## 🔌 How to Flash via Command Line

If you prefer using `esptool.py`, put your device into bootloader mode (Hold **PRG**, click **RST**, release **PRG**) and run the following command:

### Linux / macOS
```bash
esptool.py --chip esp32 --port /dev/ttyUSB0 write_flash -z 0x0 firmware.factory.bin
```

### Windows (PowerShell)
```powershell
esptool.py --chip esp32 --port COM3 write_flash -z 0x0 firmware.factory.bin
```
*(Make sure to replace `/dev/ttyUSB0` or `COM3` with your device's actual serial port interface).*

---

## 🛠️ About & Credits

* **Target Hardware:** Heltec WiFi LoRa 32 V2.1 (ESP32 / SX1276)
* **Upstream Project:** [Meshtastic](https://meshtastic.org)
* **Upstream Repository:** Forked and automated from [eeEUSERee/meshtastic_heltecv2](https://github.com)

*Disclaimer: This repository provides automated bleeding-edge development builds. Features may be experimental or unstable compared to official stable releases.*
