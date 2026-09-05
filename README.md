# SHA-256 & Multi-Format Hasher for GTM

A lightweight, synchronous variable template for **Google Tag Manager (Web Containers)** with pure-JS UTF-8 hashing and universal **E.164 Phone Normalization**.

Runs 100% in GTM's native sandboxed JavaScript engine with **zero external script injection**, **zero network calls**, and **full CSP compliance**.

---

## Supported Output Formats

| Format | Output Example | Typical Use Case |
| :--- | :--- | :--- |
| **SHA-256 (HEX)** | `e3b0c44298fc1c149afbf4c8996fb924...` | Ad conversion APIs & customer matching |
| **SHA-256 (Base64)** | `47DEQpj8HBSa+/TImW+5JCeuQeRkm5NM...` | Custom APIs / CDPs |
| **MD5 (HEX)** | `d41d8cd98f00b204e9800998ecf8427e` | Legacy pixels / CRM matching |
| **MD5 (Base64)** | `1B2M2Y8AsgTpgAmY7PhCfg==` | Base64-encoded digests |
| **Base64** | `dGVzdEBleGFtcGxlLmNvbQ==` | Standard encoding |
| **None** | `8801712345678` or `+15551234567` | Raw normalization without hashing |

---

## Normalization Options

* **Trim whitespace:** Strips leading and trailing spaces.
* **Lowercase conversion:** Standardizes case for emails and names.
* **Phone normalization (E.164):**
  * **Digits Only:** Formats without symbols or plus sign (`15551234567`).
  * **Leading Plus Sign:** Formats strictly with `+` (`+15551234567`).
  * **Multi-script conversion:** Converts Arabic-Indic (`٠-٩`), Persian (`۰-৯`), and Bengali (`০-৯`) digits to ASCII.
  * **Country code resolution:** Preserves international prefixes or auto-injects default country code for local numbers.

---

## Installation

1. Download [`SHA-256 Hasher.tpl`](./SHA-256%20Hasher.tpl).
2. In Google Tag Manager, go to **Templates** → **Variable Templates** → **New**.
3. Click menu (**⋮**) → **Import**, select `SHA-256 Hasher.tpl`, and click **Save**.

---

## Developer

**Md Kalimullah** — Web Analytics Pro  
LinkedIn: [https://www.linkedin.com/in/kalimullahh/](https://www.linkedin.com/in/kalimullahh/)
