# Smart Hasher & E.164 Phone Formatter for GTM

A lightweight, instant variable template for **Google Tag Manager (Web Containers)** providing pure-JS UTF-8 hashing (SHA-256, MD5, Base64) and universal **E.164 Phone Normalization**.

Runs 100% in GTM's native sandboxed JavaScript engine with **zero external script injection**, **zero network calls**, and **full CSP compliance**.

---

## Why This Exists

Standard GTM setups face severe limitations with hashing in Web containers:
1. GTM's built-in `sha256` API is asynchronous and cannot be used in Variable templates (which require synchronous returns).
2. Third-party tags often inject external CDN scripts (`v9.js`, etc.) that get blocked by ad-blockers, tracking prevention, or strict Content Security Policies.

This template embeds a synchronous, pure-JS UTF-8 digest engine directly into the GTM Sandboxed Macro.

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

1. Download [`template.tpl`](./template.tpl).
2. In Google Tag Manager, go to **Templates** → **Variable Templates** → **New**.
3. Click menu (**⋮**) → **Import**, select `template.tpl`, and click **Save**.

---

## Usage

1. Create a new Variable in GTM.
2. Select **Synchronous Hasher & E.164 Normalizer** as the variable type.
3. Choose your input variable (e.g. `{{DLV - email}}`, `{{DLV - phone}}`), select the output format, and configure normalization.

---

## Developer

**Md Kalimullah** — Web Analytics Pro  
LinkedIn: [https://www.linkedin.com/in/kalimullahh/](https://www.linkedin.com/in/kalimullahh/)
