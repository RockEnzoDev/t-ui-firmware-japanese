# T-Deck TFT firmware build

- Source revision: `db62ef232ad8a935b698614212ab9bbf97849012` (`Add Japanese text support for T-Deck UI`)
- PlatformIO environment: `t-deck-tft`
- Firmware version: `2.8.0.cb582ba`
- Build result: successful on 2026-10-21 (ESP32-S3, T-Deck TFT, 16 MB flash)

## Files

| File | Size | SHA-256 |
|---|---:|---|
| `firmware-t-deck-tft-2.8.0.cb582ba.bin` | 4.19 MiB | `c44047e78ef8dc90bf7798716315fafec3e3b37bf1fdea5c0b6c4a0f4c82b5bc` |
| `firmware-t-deck-tft-2.8.0.cb582ba.factory.bin` | 4.26 MiB | `ec3434d608a70ea95229f548a4ad2b155c490a9c4b462432c1e279c1c94b3e2e` |
| `littlefs-t-deck-tft-2.8.0.cb582ba.bin` | 3.38 MiB | `ea2b5c198d703affe5442be0441fff68ce83c3e1019f6333b7d2826e4617cb0b` |

- `firmware-...bin`: application image for the app partition.
- `firmware-...factory.bin`: combined bootloader, partition table, boot app, and application image.
- `littlefs-...bin`: LittleFS filesystem image, kept separate from the factory image.

The factory image does not contain the LittleFS image. Use the flashing method and offsets appropriate for the T-Deck TFT and its 16 MB partition layout. These files are build outputs; the firmware has not been tested on a physical device.

## Build

Command: `pio run -e t-deck-tft`

On the Windows build host, Windows Application Control blocked the GCC `lto-wrapper.exe`. The successful build used this machine-local `platformio_local.ini` override (the repository ignores `platformio_local*.ini`):

```ini
[env:t-deck-tft]
build_unflags =
  -std=c++11
  -std=gnu++11
```

