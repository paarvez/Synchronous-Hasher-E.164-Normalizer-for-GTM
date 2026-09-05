# SHA-256 & Multi-Format Hasher for GTM

A high-performance, synchronous variable template for **Google Tag Manager (Web Containers)** with universal **E.164 Multi-Country Phone Normalization**.

Runs 100% in GTM's native sandboxed JavaScript engine with **zero external script injection**, **zero network calls**, and **full CSP compliance**.

---

## Supported Output Formats

| Format | Output Example | Target Platforms |
| :--- | :--- | :--- |
| **SHA-256 (HEX)** | `e3b0c44298fc1c149afbf4c8996fb924...` | Meta CAPI, Google Ads Enhanced Conversions, TikTok Events API, Snapchat CAPI, Pinterest |
| **SHA-256 (Base64)** | `47DEQpj8HBSa+/TImW+5JCeuQeRkm5NM...` | Custom APIs / CDPs |
| **MD5 (HEX)** | `d41d8cd98f00b204e9800998ecf8427e` | Legacy pixels / CRM matching |
| **MD5 (Base64)** | `1B2M2Y8AsgTpgAmY7PhCfg==` | Base64-encoded MD5 digests |
| **Base64 (Raw)** | `dGVzdEBleGFtcGxlLmNvbQ==` | Payload obfuscation / basic encoding |
| **None** | `8801712345678` or `+15551234567` | Raw E.164 normalization without hashing (for tags that auto-hash) |

---

## Universal Multi-Country Phone Normalization (E.164)

Standardizes customer phone numbers from any country and input format into strict advertising platform standards:

* **Platform Standards Supported:**
  * **Meta CAPI / Snapchat / Pinterest:** Strips all non-digits, leading zeros, and **excludes `+` sign** (e.g. `8801712345678`, `15551234567`).
  * **Google Ads / TikTok Events API / GA4:** Strictly formats to **`+E.164`** with leading `+` sign (e.g. `+8801712345678`, `+15551234567`).
* **Multi-Script Numeral Conversion:** Automatically translates **Arabic-Indic** (`٠-٩`), **Eastern-Arabic / Persian** (`۰-৯`), and **Bengali** (`০-৯`) digits into standard ASCII (`0-9`).
* **Global Country Code Resolution:** Preserves existing international prefixes (`+`, `00`), or auto-injects configurable country code (e.g. `1` US, `44` UK, `971` UAE, `880` BD) when customers enter local national numbers.

---

## Installation

1. Download [`SHA-256 Hasher.tpl`](./SHA-256%20Hasher.tpl).
2. In Google Tag Manager, navigate to **Templates** → **Variable Templates** → **New**.
3. Click the top-right menu icon (**⋮**) → **Import**, select `SHA-256 Hasher.tpl`, and click **Save**.

---

## Developer

**Md Kalimullah** — Web Analytics Pro  
LinkedIn: [https://www.linkedin.com/in/kalimullahh/](https://www.linkedin.com/in/kalimullahh/)
