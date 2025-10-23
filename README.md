# Comprehensive DNS Allowlist for Strict Ad Blocking

This repository provides a curated **DNS allowlist** (whitelist) built to make the most aggressive DNS blocklists usable in home and enterprise-lab environments **without breaking legitimate services**.

It is optimized for [AdGuard DNS](https://adguard-dns.io) but can also be used with [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome), [Pi-hole](https://pi-hole.net/), and other DNS-filtering systems.

---

## Purpose

Aggressive DNS blocklists increase privacy and reduce telemetry but can block essential services such as software activation, app store updates, cloud sync, and certificate validation.

This project provides a **strict-mode allowlist** that restores critical functionality for legitimate desired ecosystems while (mostly) keeping advertising, tracking, and telemetry endpoints blocked.

The allowlist is separated into functional sections, each annotated for clarity and risk-awareness:

- **Functionally Required Sections**
  - `AUTHN_IDP` – Authentication, identity, and SSO (Okta, Auth0, OneLogin)
  - `PKI_CERT_VALIDATION` – Certificate and OCSP/CRL validation
  - `DNS_TIME_CONNECTIVITY` – Connectivity and NTP/time sync endpoints
  - `DEV_REPOS` – Software repositories (GitHub, npm, PyPI)
  - `EMAIL` and `EMAIL_SECURITY_DELIVERY` – Core and secure mail services
  - `SECURITY_VENDORS` – EDR, antivirus, and threat intelligence platforms
  - `SOFTWARE_UPDATES` – Vendor update and activation servers
  - `OS_VENDOR_*` – Apple, Google, Microsoft, and Amazon functional ecosystems
  - `VENDOR_UBIQUITI` – UniFi/Protect/Network connectivity

- **Optional and Situational Sections**
  - `INFRA_HARDWARE_VENDOR` – Synology and device management services
  - `VENDOR_PC_HARDWARE` – ASUS, Gigabyte, and related update hosts
  - `NETWORK_AND_UTILITY_SERVICES` – Cloudflare, Fastly, OpenDNS, Speedify
  - `COMMS_AND_VIDEO_INFRA` – Teams, Zoom, Skype, and STUN/TURN hosts
  - `BUSINESS_CLOUD_AND_PRODUCTIVITY` – Microsoft 365, Slack, developer APIs
  - `PAYMENTS_FINANCE` – PayPal, Stripe, Adyen, Moneris, Interac
  - `ECOMMERCE_PLATFORMS` – Shopify and associated CDNs
  - `IOT_SMARTHOME` – Ring, Anker, Mysa, and related IoT infrastructure
  - `GAMING_SERVICES_AND_PLATFORMS` – Steam, Epic, Riot, Xbox, Ubisoft, ESO
  - `BOOKS_MEDIA` – Kobo, NovelBin, and digital reading platforms
  - `P2P_TORRENTS` – Torrents and P2P clients (disabled by default)
  - `CDN_DNS_OPT` – General CDN and network optimization endpoints
  - `OTHER_VENDOR_DOMAINS` – Adobe, Rakuten, and miscellaneous vendor services
  - `SOCIAL_MEDIA` – Facebook, Reddit, Twitter/X, Instagram, LinkedIn, TikTok

Each section header identifies **required vs optional** functionality.  
Root-level or near-root domains likely to host telemetry, analytics, or ad-serving endpoints include inline comments:

```text
@@||badcompany.com^ # possible ads/tracking on subdomains
````

This allows administrators to quickly audit and toggle wildcards or re-scope entries as needed.

---

## Compatibility

| Platform                  | Compatibility | Notes                                           |   |                   |
| ------------------------- | ------------- | ----------------------------------------------- | - | ----------------- |
| **AdGuard DNS**           | ✅ Native      | Fully compatible as-is (uses `@@                |   | domain^` syntax). |
| **AdGuard Home**          | ✅ Compatible  | May require LF line endings.                    |   |                   |
| **Pi-hole**               | ✅ Compatible  | Add via *Group Management → Adlists → Raw URL*. |   |                   |
| **pfBlockerNG / Unbound** | ⚙️ Supported  | Convert to plain domain format before import.   |   |                   |
| **NextDNS**               | ⚙️ Supported  | Add under *Custom Allowlist*.                   |   |                   |

---

## Usage

1. Copy the **raw URL** of `allowlist.txt`:
   ```
   https://raw.githubusercontent.com/jposluns/dns_lists/refs/heads/main/allowlist.txt
   ```
2. Add it to your DNS filter configuration, or copy paste the contents to custom user rules if your tool doesn't allow referencing external lists.
3. Apply changes and flush DNS caches.
4. Validate that essential services operate normally (see below).

---

## Testing

After applying filters, verify that legitimate services remain functional:

* Apple ID login, App Store, iCloud, and software updates
* Windows Update, Microsoft 365, Teams, and Outlook
* Google Play, Gmail, and Android system updates
* UniFi / Protect controllers
* Payment processing (PayPal, Stripe, Interac)
* Steam, Xbox Live, Epic Games, and Discord connectivity

Recommended validation tools:

* [AdGuard Test Page](https://adguard.com/test.html)
* [DNSLeakTest](https://www.dnsleaktest.com/)
* [Whoer.net](https://whoer.net/)

---

## Contributions

Pull requests and issue reports are encouraged.
When submitting changes, include:

* The affected domain(s)
* The section name (`SECURITY_VENDORS`, `OS_VENDOR_APPLE`, etc.)
* The reason for inclusion or removal
* Service(s) impacted by the change

---

## License

**Creative Commons Attribution – NonCommercial 4.0 International (CC BY-NC 4.0)**

You may **use, copy, and modify** this list for **personal or internal business use**.
Commercial redistribution, resale, or bundling into paid products or services is **prohibited**.

Full text: [https://creativecommons.org/licenses/by-nc/4.0/](https://creativecommons.org/licenses/by-nc/4.0/)
