# Threadline Releases

Official pre-built binaries and release notes for **Threadline** — the local-first CPU layer of *The Engineering Protocol Stack* for technical leaders.

Everything lives in your local SQLite database on your device. Nothing leaves your machine.

Companion to [TrustLine](https://github.com/guillemf/trustline-releases) (the WAN layer).

---

## Downloads

Download the latest version for your platform:

| Platform | Architecture | Installer | Direct Download |
|---|---|---|---|
| **macOS** | Apple Silicon (`M1/M2/M3/M4`) | DMG | [Threadline_aarch64.dmg](https://github.com/guillemf/threadline-releases/releases/latest/download/Threadline_0.1.0_aarch64.dmg) |
| **macOS** | Intel (`x86_64`) | DMG | [Threadline_x64.dmg](https://github.com/guillemf/threadline-releases/releases/latest/download/Threadline_0.1.0_x64.dmg) |
| **Windows** | 64-bit | Setup EXE (NSIS) | [Threadline_x64-setup.exe](https://github.com/guillemf/threadline-releases/releases/latest/download/Threadline_0.1.0_x64-setup.exe) |
| **Linux** | 64-bit | AppImage | [Threadline_amd64.AppImage](https://github.com/guillemf/threadline-releases/releases/latest/download/threadline_0.1.0_amd64.AppImage) |
| **Linux** | 64-bit | Debian Package | [Threadline_amd64.deb](https://github.com/guillemf/threadline-releases/releases/latest/download/threadline_0.1.0_amd64.deb) |

*For all historical versions and checksums, see the [Releases page](https://github.com/guillemf/threadline-releases/releases).*

---

## Operating System Installation Notes

Threadline is currently unsigned (independent software), so modern OS security systems will show an initial notice on first run:

### macOS
Gatekeeper blocks execution on first open (*"Threadline can't be opened because it is from an unidentified developer"*):
1. Open your **Applications** folder.
2. **Right-click** (or Control-click) `Threadline.app` and choose **Open**.
3. Click **Open** in the confirmation dialog. (You only need to do this once).
4. *Or from your terminal:*  
   ```sh
   xattr -dr com.apple.quarantine /Applications/Threadline.app
   ```

### Windows
Windows SmartScreen will display: *"Windows protected your PC"*:
1. Click **More info**.
2. Click **Run anyway**.

### Linux
Make the AppImage executable:
```sh
chmod +x Threadline_*.AppImage
./Threadline_*.AppImage
```

---

## Privacy & Updates

The Threadline application queries this repository at most once daily to check if a newer version has been published and notify you in-app. This check:
- Transmits **no** personal information, item titles, notes, or telemetry.
- Is a lightweight, public read of the release tag.

## Licence

Threadline is proprietary software offered under the [Threadline End User Licence Agreement](https://engineeringprotocolstack.com/eula).
