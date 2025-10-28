# DNS ALLOW AND BLOCK LISTS

### Overview

This repository provides a set of curated DNS allow and block lists in AdGuard format, intended for use **alongside highly restrictive full blocking configurations**. For example, when enabling all available filters and blocking options in [AdGuard DNS](https://adguard-dns.io). Such aggressive filtering is excellent for privacy and security but often breaks legitimate functionality in normal multi-user households (adults, children, guests). This allow list restores access to critical operating system updates, networking tools, authentication, gaming, and some social media services while keeping telemetry, advertising, and tracking exposure **to a minimum**.

The DNS allow list is designed as a broadly compatible, drop-in configuration to ensure that desired services work reliably across all modern platforms. It includes validated FQDNs for Apple, Microsoft, Google, UniFi, and other vendors to prevent restrictive block lists from breaking critical functionality. For ease of deployment and compatibility, the list also includes popular social media, gaming, file-sharing, and communication services. This makes it suitable for environments seeking balance between usability and security without requiring heavy customization.

Those seeking a tighter, privacy-focused configuration should treat this as a **baseline** or **reference** only. The intent of this list is **stability and simplicity**, not maximum privacy enforcement. Updates will occur **only when necessary** to maintain reliability or reflect vendor changes.

---

### File Structure

#### **allowlist.txt**
Contains all known-good FQDNs (fully qualified domain names) that should be explicitly permitted, even when broad filtering or wildcard blocking is enabled.  
Each entry has been validated to ensure it supports legitimate functionality such as:
- Operating system and app updates  
- Device enrolment and authentication  
- Essential connectivity and CDN resolution  
- Cloud and communication services

This list is the foundation for restoring functionality within otherwise aggressive blocking environments.

#### **blocklist.txt**
Contains additional FQDNs that should be **explicitly denied**, even if broader wildcard allowances might otherwise include them.  
These entries were either:
- Missing from common community block lists, or  
- Added to prevent telemetry, tracking, or advertising when a wildcard allow rule was required for functionality  

The block list acts as a fine-tuning layer to **correct overbroad allowances** while maintaining service stability.

---

### Usage

Clone or download the latest version and import it into AdGuard, Pi-hole, or your preferred DNS filtering system.  
Apply **allowlist.txt** before other rules to restore required functionality, and **blocklist.txt** to suppress residual telemetry or unwanted network calls.

---

### License

This repository and its contents are licensed under the  
**Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** license.

You are free to share and adapt the material for **personal or organizational use**, provided that:
- Proper attribution is given, and  
- The material **is not used for commercial purposes** or sold as part of a paid product or service.  

For full license details, see:  
[https://creativecommons.org/licenses/by-nc/4.0/](https://creativecommons.org/licenses/by-nc/4.0/)
