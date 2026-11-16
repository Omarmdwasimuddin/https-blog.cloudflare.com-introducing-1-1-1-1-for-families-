# Router-e Cloudflare 1.1.1.1 for Families Setup Guide

> **Goal:** Router-e DNS set kore pura home network-e **Malware + Adult Content** block kora.
> **Shomoy lagbe:** prai 5-10 minute

---

## DNS Address (Malware + Adult Content Block)

| Type | Primary DNS | Secondary DNS |
|------|-------------|---------------|
| **IPv4** | `1.1.1.3` | `1.0.0.3` |
| **IPv6** | `2606:4700:4700::1113` | `2606:4700:4700::1003` |

---

## Quick Checklist

- [ ] Router admin panel-e login korlam
- [ ] DNS setting khuje pelam
- [ ] Manual DNS boshalam (IPv4)
- [ ] IPv6 DNS boshalam (jodi router support kore)
- [ ] Save kore router reboot dilam
- [ ] Device-e reconnect / DNS flush korlam
- [ ] Test URL diye check korlam
- [ ] Browser-er Secure DNS check korlam

---

## Step-by-Step Process

### Step 1: Router Admin Panel-e Login Koro

1. Browser open kore router-er IP address dao:
   - `192.168.0.1` ba
   - `192.168.1.1`
   - (Router-er niche sticker-e IP lekha thake)
2. Admin username ar password dao.
   - Default username/password-o sticker-e thake.
   - Tumi age change kore thakle seta use koro.

---

### Step 2: DNS Setting Khuje Ber Koro

Router-er brand onujayi jaygata alada hoy. Common jaygagulo:

- **WAN / Internet / Network** settings-er moddhe "DNS" option
- Kono kono router-e **DHCP / LAN** settings-e DNS dewar option thake

> **Tip:** Menu-te "DNS", "Primary DNS", "Static DNS" ba "Manual DNS" word khujo.

---

### Step 3: DNS Manually Boshao

DNS mode **Auto / ISP** theke **Manual / Static** e change koro, tarpor boshao:

```
Primary DNS   : 1.1.1.3
Secondary DNS : 1.0.0.3
```

Router IPv6 DNS-o chay hole:

```
Primary DNS   : 2606:4700:4700::1113
Secondary DNS : 2606:4700:4700::1003
```

---

### Step 4: Save Kore Router Reboot Koro

1. **Save / Apply** button chapo.
2. Router **restart / reboot** koro.

---

### Step 5: Device-e DNS Refresh Koro

- Connected device-gulo **Wi-Fi off kore abar on** koro (reconnect).
- Laptop (Windows) hole Command Prompt-e ei command chalao:

```
ipconfig /flushdns
```

---

### Step 6: Test Koro

Ei duita link browser-e open koro:

| Test URL | Expected Result |
|----------|-----------------|
| https://nudity.testcategory.com/ | **Block hobe** (adult content filter kaj korche) |
| https://malware.testcategory.com/ | **Block hobe** (malware filter kaj korche) |

Dutoi block hole setup **thik ache**.

---

## Kichu Jinish Dekhe Rakho

### 1. ISP-er Locked Router
Kono kono ISP-er router-e DNS change korar option thake na.
- ISP-ke bolo unlock korte, **ba**
- Nijer router kine ISP-er router-er pichone connect koro.

### 2. Browser-er Secure DNS / DoH
Chrome, Firefox-er Secure DNS on thakle oi browser router-er DNS bypass kore nijer DNS use korte pare.
- Oi setting **off** koro, **ba**
- Cloudflare family DoH URL set koro:

```
https://family.cloudflare-dns.com/dns-query
```

### 3. IPv6
ISP IPv6 dile ar router-e IPv6 DNS set na korle kichu traffic filter bypass korte pare. Tai IPv6 DNS-o set kora bhalo.

### 4. Mobile Data / Onno Network
Ei filter **shudhu ei router-er Wi-Fi-te** kaj korbe. Mobile data ba onno network-e kaj korbe na.

### 5. Foolproof Na
DNS filter 100% foolproof na. Tech-savvy keu DNS change kore bypass korte pare. Eta ekta **extra protection layer** hishebe dhoro.

---

## Problem Hole Ki Korbe (Troubleshooting)

| Problem | Solution |
|---------|----------|
| Site block hocche na | Device reconnect koro, `ipconfig /flushdns` chalao, browser-er Secure DNS check koro |
| Router-e DNS option nei | ISP-er locked router hote pare, ISP-ke jogajog koro |
| Internet cholche na | DNS address thik type korechho kina check koro, na hole Auto DNS-e fire jao |
| Kono valid site vul kore block | https://radar.cloudflare.com/categorization-feedback/ e anonymous feedback dao |

---

## Reference

- Cloudflare Blog: https://blog.cloudflare.com/introducing-1-1-1-1-for-families/
- Cloudflare Setup Docs: https://developers.cloudflare.com/1.1.1.1/setup/
