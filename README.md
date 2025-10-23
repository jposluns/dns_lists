# Comprehensive DNS Allowlist for Strict Ad Blocking

This repository provides a curated **DNS allowlist** (whitelist) built to make the most aggressive DNS blocklists usable in home and lab environments **without breaking legitimate services**.

It is optimized for [AdGuard DNS](https://adguard-dns.io) but can also be used with [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome), [Pi-hole](https://pi-hole.net/), and other DNS-filtering systems.

---

## Purpose

Aggressive DNS blocklists increase privacy and reduce telemetry but can block essential services such as software activation, app store updates, cloud sync, and certificate validation. Non-essential services in homes such as gaming and social media may often also be blocked.

This project provides a **strict-mode allowlist** that restores critical functionality for legitimate & desired ecosystems while (mostly) keeping advertising, tracking, and telemetry endpoints blocked.

---

## Usage

1. Copy the **raw URL** of `allowlist.txt`:
   ```
   https://raw.githubusercontent.com/jposluns/dns_lists/refs/heads/main/allowlist.txt
   ```
2. Add it to your DNS filter configuration, or copy paste the contents to custom user rules if your tool doesn't allow referencing external lists.
3. Apply changes and flush DNS caches.
4. Validate that essential services operate normally.

---

## License

**Creative Commons Attribution – NonCommercial 4.0 International (CC BY-NC 4.0)**

You may **use, copy, and modify** this list for **personal or internal business use**.
Commercial redistribution, resale, or bundling into paid products or services is **prohibited**.

Full text: [https://creativecommons.org/licenses/by-nc/4.0/](https://creativecommons.org/licenses/by-nc/4.0/)
