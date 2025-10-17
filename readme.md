# Meshtastic Heltec V2.1 Auto-Builds

This repository automatically builds the **Meshtastic firmware** for the  
**Heltec WiFi LoRa 32 V2** board every night (development branch).

## Downloads
- Go to the [Actions tab](../../actions) → click the latest run → download the `heltec-v2-firmware` artifact.
- Each artifact includes:
  - `firmware.bin`
  - `firmware.factory.bin`
- Or go to releases

## Flashing
Example (Linux/macOS):
```bash
esptool.py --chip esp32 --port /dev/ttyUSB0 write_flash -z 0x0 firmware.factory.bin
