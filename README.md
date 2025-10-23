# Comprehensive DNS Allowlist for Strict Ad Blocking

This repository provides a curated **DNS allowlist** (whitelist) designed to make the strictest and most comprehensive DNS blocklists usable in home environments without breaking legitimate services.

It is optimised for [AdGuard DNS](https://adguard-dns.io) but can be used with [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome), [Pi-hole](https://pi-hole.net/), or similar DNS-filtering platforms with only minor format adjustments.

---

## 🧭 Purpose

Aggressive DNS blocklists can improve privacy and reduce telemetry, but they often block essential functionality such as software activation, app store updates, payment processing, and authentication.

This project provides a **safe-use allowlist** that restores critical functionality for legitimate services while keeping ad, telemetry, and tracking domains blocked.

It allows you to run **maximum-strength blocking** while maintaining (mostly) seamless access to trusted ecosystems including:

- **Apple** – iCloud, iTunes, App Store, Apple Pay, iMessage, activation, certificate validation  
- **Microsoft** – Windows Update, Office 365, Xbox Live, Outlook, Teams, Edge, activation  
- **Google / Android** – Play Store, push notifications, Gmail, Chrome Sync, Android backup, fonts, analytics APIs required for app operation  
- **Payment and Financial Gateways** – PayPal, Stripe, Adyen, Square, Moneris, Plaid, Google Pay, Apple Pay, Interac  
- **Cloud and CDN Services** – Cloudflare, Akamai, Fastly, Amazon AWS, Azure, Google Cloud, Firebase, CloudFront  
- **Security and Threat Intel Vendors** – Palo Alto Networks, CrowdStrike, Fortinet, Sophos, Mimecast, Proofpoint, ESET, Trend Micro, Cisco Talos  
- **Vendors and Hardware Ecosystems** – ASUS (Armoury Crate, MyASUS, ROG), Gigabyte, Synology, UniFi (Ubiquiti), NVIDIA, Adobe Creative Cloud, LinkedIn CDN  
- **Gaming and Entertainment** – Steam, Epic Games, Battle.net, Elder Scrolls Online, Ubisoft, Square Enix, ArenaNet, Xbox Live, PlayStation Network, Discord, Zoom, Prime Video  
- **Email and Collaboration** – Microsoft 365, Google Workspace, Slack, Mimecast, Zoom, Okta SSO  
- **Time and NTP Services** – Apple, Google, Microsoft, Cloudflare, pool.ntp.org  
- **Trusted Public DNS Resolvers** – 1.1.1.1 (Cloudflare), 8.8.8.8 (Google DNS), OpenDNS Umbrella, Quad9  
- **Other Critical Infrastructure** – Certificate Revocation Lists (CRL/OCSP), telemetry for endpoint security, legitimate firmware and driver updates  

---

## 🧩 Compatibility

| Platform | Compatibility | Notes |
|-----------|---------------|-------|
| **AdGuard DNS** | ✅ Native | Direct import via *Custom Filter URL*. |
| **AdGuard Home** | ✅ Compatible | May require LF line endings or removal of comment lines. |
| **Pi-hole** | ✅ Compatible | Add via *Group Management → Adlists* using the raw GitHub URL. |
| **pfBlockerNG / Unbound** | ⚙️ Supported | Convert to domain format before import. |
| **NextDNS** | ⚙️ Supported | Add URLs under *Custom Allowlist / Denylist*. |

---

## ⚙️ Usage

1. Choose your desired list (`allowlist.txt`, `blacklist.txt`, etc.).
2. Copy the **raw URL**, for example:  
   `https://raw.githubusercontent.com/<username>/<repo>/main/allowlist.txt`
3. Add it to your platform’s filter configuration:
   - **AdGuard DNS** – *Dashboard → Custom Filters → Add URL*  
   - **AdGuard Home** – *Filters → DNS Blocklists → Add custom list*  
   - **Pi-hole** – *Group Management → Adlists → Add URL*  
4. Apply changes and flush DNS caches.

---

## 🧪 Testing

After applying filters:
- Confirm that essential services (e.g., Apple Pay, Microsoft Updates, Gmail, Steam) function normally.
- Validate blocking behaviour with:
  - [dnsleaktest.com](https://www.dnsleaktest.com/)
  - [AdGuard Test Page](https://adguard.com/test.html)
  - [whoer.net](https://whoer.net/)

---

## 🧭 Contributions

Pull requests and issue reports are welcome.  
When submitting changes, include:
- The affected domain(s)
- The reason for inclusion or removal
- Service or application impacted

---

## ⚖️ License

**Creative Commons Attribution – NonCommercial 4.0 International (CC BY-NC 4.0)**  

You may **use, copy, and modify** this work for **personal or internal business use only**.  
Commercial resale, redistribution for profit, or bundling into paid products or services is **prohibited**.

Full license text: [https://creativecommons.org/licenses/by-nc/4.0/](https://creativecommons.org/licenses/by-nc/4.0/)
