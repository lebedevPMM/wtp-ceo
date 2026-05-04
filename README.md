# ceo.wtp.ae — Ivan Olenichev Personal Handoff Kit

Personal contact-handoff page for **Ivan Olenichev**, Founder & CEO of WTP.
Designed for two scenarios:

1. **Quick meet handoff** — opponent may not remember who Ivan is. Page re-introduces him in 5 seconds.
2. **Post-meeting / event handoff** — partner or end-client follow-up, English only, optional event toggle via `?event=may6`.

**Live:**
- Production: <https://ceo.wtp.ae>
- Cloudflare Pages: <https://wtp-ceo.pages.dev>
- Mirror: <https://lebedevpmm.github.io/wtp-ceo/>

---

## Distribution Kit (in `qr/`)

| File | When to use |
|---|---|
| `qr-ceo-wtp-ae-card.png` | **Print-ready card** — QR + URL + name. A6/business card back. |
| `qr-ceo-wtp-ae-brand.png` | **Branded QR** (cream + WTP logo). For decks, slides, email signature. |
| `qr-ceo-wtp-ae-bw.png` | **Pure black on white** — most reliable scan, smallest size, any printer. |
| `qr-ceo-wtp-ae-clean.png` | **Cream, no logo** — softest look, max scan reliability. |
| `ivan-olenichev.vcf` | **vCard** — open on iPhone/Android → "Add to Contacts". Saves Ivan in one tap. |

All QR codes encode `https://ceo.wtp.ae` with **30% error correction** — they survive logo overlay, partial damage, low-contrast surfaces.

---

## NFC Tag — Tap-to-Open (iPhone & Android)

Modern iPhones (XS and newer, iOS 14+) read NFC URL tags **without any app**.
Tap the back of the phone on the tag → notification appears → tap to open `ceo.wtp.ae`.

### Tag selection

| Tag chip | Storage | Best for |
|---|---|---|
| **NTAG213** | 144 bytes | Stickers, business cards (cheapest) |
| **NTAG215** | 504 bytes | Recommended — fits URL + future expansion |
| **NTAG216** | 888 bytes | Overkill for one URL |

Forms:
- **Sticker** — 25 mm round, glue under business card / phone case / event badge
- **PVC card** — credit-card sized, looks like a metal/black business card with WTP logo on front
- **Keyring fob** — for daily-carry handoff

Where to buy: Aliexpress / Amazon / GoToTags. Search `NTAG215 sticker 25mm` (~$1-2 each in bulk).

### How to program (one-time, ~2 min per tag)

**On iPhone:**
1. Install free app **"NFC Tools"** by wakdev (App Store)
2. Open → **Write** → **Add a record** → **URL / URI**
3. Enter `https://ceo.wtp.ae` → OK
4. Tap **Write** → hold the tag against the top of the iPhone
5. App confirms write. Done.

**On Android (faster):** same app **"NFC Tools"** by wakdev (Play Store), same flow. Android writes faster and more reliably than iOS for bulk programming.

### Optional: lock the tag (prevents accidental overwrite)
After writing, in NFC Tools → **Other** → **Lock tag** → confirm. Tag is read-only forever.

### What the user sees

- iPhone: notification banner with `ceo.wtp.ae` → tap → Safari opens.
- Android: pop-up "Open in browser?" → tap → Chrome opens.
- No app needed on either side. Just hardware.

---

## vCard (.vcf) — Save Contact in One Tap

`ivan-olenichev.vcf` contains: name, role, company, email, LinkedIn, Telegram, URL, Dubai address.

**Use it for:**
- **Email signature** — attach the .vcf, recipient taps once → contact saved with all channels.
- **AirDrop on iPhone** — open the .vcf in Files → share → AirDrop to opponent's iPhone → they tap "Add Contact".
- **WhatsApp / Telegram chat** — send as a file.
- **Live serving** — accessible at <https://ceo.wtp.ae/ivan-olenichev.vcf> after deploy.

To regenerate after edits: just edit the `.vcf` text file. Standard vCard 3.0 format.

---

## Print Spec

| Use | Size | Format |
|---|---|---|
| Business card back | 85×55 mm at 300 dpi | `qr-ceo-wtp-ae-card.png` (resize, keep aspect) |
| A6 handout | 105×148 mm at 300 dpi | `qr-ceo-wtp-ae-card.png` directly |
| Sticker on laptop / device | 50×50 mm | `qr-ceo-wtp-ae-bw.png` |
| Slide footer / email sig | 200×200 px screen | `qr-ceo-wtp-ae-brand.png` (resize) |

Min printed QR module size: **0.5 mm** per cell. Anything smaller and phone cameras struggle.

---

## How to update the page

```bash
# edit index.html, then:
git add index.html && git commit -m "..." && git push
```

Cloudflare Pages auto-builds on push (project: `wtp-ceo`).
GitHub Pages mirror also rebuilds automatically.

URL `https://ceo.wtp.ae` does NOT change — QR codes and NFC tags stay valid forever.

---

## Files

```
links-ceo/
├── index.html              # the page itself
├── ivan-olenichev.vcf      # vCard for "Save Contact"
├── README.md               # this file
└── qr/
    ├── qr-ceo-wtp-ae-card.png    # print-ready (with URL + name caption)
    ├── qr-ceo-wtp-ae-brand.png   # cream + W logo
    ├── qr-ceo-wtp-ae-bw.png      # plain black on white
    └── qr-ceo-wtp-ae-clean.png   # cream, no logo
```
