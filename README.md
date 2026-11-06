# PS5 Linux Loader Catalog

A custom source for [PS5 Payload Manager](https://github.com/itsPLK/ps5-payload-manager) that lists
[soniciso1/ps5-linux-loader](https://github.com/soniciso1/ps5-linux-loader).
Format: [CUSTOM_REPOSITORIES.md](https://github.com/itsPLK/ps5-payload-manager/blob/main/CUSTOM_REPOSITORIES.md).

## Add this source

1. Open Payload Manager → **Settings** → **Manage Sources**.
2. Click **Add Source** and paste:
   ```
   https://raw.githubusercontent.com/Ayan4k/ps5-linux-loader-catalog/main/payloads.json
   ```
3. Press **Add**. "PS5 Linux Loader" appears under the **Linux** category.

## Before launching

- Settings → System → Power Saving → Features Available in Rest Mode → **Supply Power to USB Ports: Always**.
- Disable HDMI Device Link.
- Disable etaHEN/kstuff (incompatible; the console freezes instead of entering rest mode).
- After launch the console enters rest mode. Wait for a static orange LED, then press power. A white LED means Linux is booting.

Full setup, supported firmware and troubleshooting: see the
[upstream README](https://github.com/soniciso1/ps5-linux-loader#readme).

## Updating the catalog

1. Open the new release on [soniciso1/ps5-linux-loader](https://github.com/soniciso1/ps5-linux-loader/releases).
2. Download the ELF and run `sha256sum ps5-linux-loader.elf`.
3. In `payloads.json`, update `url`, `version` (the tag), `last_update` and `checksum`. Keep `id` unchanged so favorites and autoload survive updates.
4. Commit. Payload Manager flags the update when the version or checksum differs.

## Notes

- This catalog only points to upstream release files and does not host binaries.
- A checksum verifies file integrity, not the author's identity. Only add sources you trust.
- Credits: loader by soniciso1, based on [ps5-linux/ps5-linux-loader](https://github.com/ps5-linux/ps5-linux-loader) (theflow, c0w).
