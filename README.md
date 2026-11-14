# MikroTik adlists collection

Automated, merged, and cleaned ad-blocking and domain-filtering lists tailored for use as **MikroTik adlists** (DNS / Web proxy filtering).

---

> ⚠️ **Note on custom rules:** 
> Since this project is primarily built for personal use, the **SEgA** custom local list may include additional domains, trackers, or specific resources that I decided to block for my own home networks.

---

## Optimization & Memory efficiency
To minimize RAM usage on MikroTik routers, all lists undergo strict preprocessing:
- Stripping comments and redundant formatting.
- Filtering out empty lines and invalid entries.
- Sorting and deduplicating unique domains in standard `0.0.0.0` hosts format.

> 💡 **Recommendation for low-resource devices:** If your MikroTik router has limited RAM, it is recommended to use the lighter **`SEgA_oisd_hosts`** list to conserve memory.

---

## Available lists

| File name | Description | Sources |
| --- | --- | --- |
| `SEgA_oisd_hosts` | Merged custom local blocklist and **OISD** domains<br>*(Recommended for weak devices)*. | Custom SEgA<br>[OISD](https://oisd.nl/) |
| `SEgA_HaGeZisMultiPROplus_hosts` | Merged custom local blocklist<br>and **HaGeZi Multi PRO++** domains. | Custom SEgA<br>[HaGeZi](https://github.com/hagezi/dns-blocklists) |
| `SEgA_oisd_HaGeZisMultiPROplus_hosts` | Combined master list containing custom local entries,<br>**OISD**, and **HaGeZi Multi PRO++**. | Custom SEgA<br>[OISD](https://oisd.nl/)<br>[HaGeZi](https://github.com/hagezi/dns-blocklists) |

---

### SEgA custom local list highlights

- **Ads & Analytics & App & Service telemetry:** Google, Amazon, Meta, Twitter, Yahoo, Yandex, Viber, TikTok, Taboola, Rakuten, Malwarebytes, MEGA, Android TV, etc.
- **Device & OS telemetry:** Apple, Samsung, Xiaomi, Huawei, OnePlus, Realme, Microsoft.

> **Note:** This blocklist is dynamic and subject to future updates!

---
## Direct raw links

Copy the required list URL to add it directly to your MikroTik DNS Adlist setup:

**SEgA + OISD:**

```text
https://raw.githubusercontent.com/esurgan/adblocklists/refs/heads/main/SEgA_oisd_hosts
```

**SEgA + HaGeZi Multi PRO++:**

```text
https://raw.githubusercontent.com/esurgan/adblocklists/refs/heads/main/SEgA_HaGeZisMultiPROplus_hosts
```
**SEgA + OISD + HaGeZi Multi PRO++:**

```text
https://raw.githubusercontent.com/esurgan/adblocklists/refs/heads/main/SEgA_osid_HaGeZisMultiPROplus_hosts
```
---

## Usage on MikroTik (RouterOS v7.15+)

You can add any of these lists directly into your MikroTik router via IP/DNS Adlist:

**SEgA + OISD:**
```routeros
/ip dns adlist
add url=https://raw.githubusercontent.com/esurgan/adblocklists/refs/heads/main/SEgA_oisd_hosts
```

**SEgA + HaGeZi Multi PRO++:**

```routeros
/ip dns adlist
add url=https://raw.githubusercontent.com/esurgan/adblocklists/refs/heads/main/SEgA_HaGeZisMultiPROplus_hosts
```

**SEgA + OISD + HaGeZi Multi PRO++:**

```routeros
/ip dns adlist
add url=https://raw.githubusercontent.com/esurgan/adblocklists/refs/heads/main/SEgA_osid_HaGeZisMultiPROplus_hosts
```
