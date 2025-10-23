# DNS ALLOW LIST — MASTER (Expanded FQDNs)

### Overview

This repository provides a curated DNS allow list in AdGuard format, intended for use **alongside highly restrictive full blocking configurations** — for example, when enabling all available filters and blocking options in [AdGuard DNS](https://adguard-dns.io). Such aggressive filtering is excellent for privacy and security but often breaks legitimate functionality in normal multi-user households (adults, children, guests). This allow list restores access to critical operating system updates, networking tools, authentication, gaming, and some social media services while keeping telemetry, advertising, and tracking exposure to a minimum.

The DNS allow list is designed as a broadly compatible, drop-in configuration to ensure that desired services work reliably across all modern platforms. It includes validated FQDNs for Apple, Microsoft, Google, UniFi, and other trusted vendors to prevent common block lists from breaking critical functionality. For ease of deployment and compatibility, the list also includes popular social media, gaming, file-sharing, and communication services. This makes it suitable for environments seeking balance between usability and security without requiring heavy customization.

Those seeking a tighter, privacy-focused configuration should treat this as a **baseline** — selectively removing sections or consolidating categories as desired. The intent is **stability and simplicity**, not maximum privacy enforcement. Updates will occur **only when necessary** to maintain reliability or reflect vendor infrastructure changes.

---

### Usage

Clone or download the latest version and import it into AdGuard, Pi-hole, or your preferred DNS filtering system. Apply this list **before** custom allow-by-exception rules to ensure core OS and cloud services continue functioning correctly.

---

### License

This repository and its contents are licensed under the  
**Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** license.

You are free to share and adapt the material for **personal or organizational use**, provided that:
- Proper attribution is given, and  
- The material **is not used for commercial purposes** or sold as part of a paid product or service.  

For full license details, see:  
[https://creativecommons.org/licenses/by-nc/4.0/](https://creativecommons.org/licenses/by-nc/4.0/)
