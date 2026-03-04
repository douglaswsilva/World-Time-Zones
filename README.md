[README.md](https://github.com/user-attachments/files/25750574/README.md)
# 🌍 World Time Dashboard

> A beautiful, live timezone converter — instantly see and convert times across every region we work with, anchored to GMT.

![Live Clocks](https://img.shields.io/badge/clocks-live-a78bfa?style=flat-square&logo=clockify&logoColor=white)
![Timezones](https://img.shields.io/badge/timezones-6-f472b6?style=flat-square)
![Format](https://img.shields.io/badge/format-AM%2FPM%20%2F%2024H-38bdf8?style=flat-square)
![Hosted on](https://img.shields.io/badge/hosted%20on-GitHub%20Pages-fbbf24?style=flat-square&logo=github&logoColor=white)
![Built with](https://img.shields.io/badge/built%20with-Claude%20AI-a78bfa?style=flat-square)

---

## ✨ Features

- **Live clocks** — all times update every second, no refresh needed
- **6 regions** — California, Brazil, Eastern Time, Switzerland & Germany, UAE, and Meridian (GMT) as the reference
- **Instant converter** — type a time in any region and all others update immediately
- **AM/PM or 24H** — toggle between formats with one click, default is AM/PM
- **Shareable text** — generates a formatted breakdown you can copy and paste into Slack, WhatsApp, or email, showing both AM/PM and 24H formats side by side
- **Auto light/dark mode** — switches based on your local time (dark from 7 PM to 7 AM, light during the day), with a manual override
- **Fully responsive** — works on mobile, tablet, and desktop

---

## 🗺️ Regions Covered

| Flag | Region | Timezone | IANA Identifier |
|------|--------|----------|-----------------|
| 🌍 | Meridian *(reference)* | GMT / UTC+0 | `Etc/GMT` |
| 🇺🇸 | California | PT (PST/PDT) | `America/Los_Angeles` |
| 🇧🇷 | Brazil | BRT/BRST | `America/Sao_Paulo` |
| 🇺🇸 | Eastern Time | ET (EST/EDT) | `America/New_York` |
| 🇨🇭 | Switzerland & Germany | CET/CEST | `Europe/Zurich` |
| 🇦🇪 | UAE | GST (UTC+4) | `Asia/Dubai` |

---

## 🚀 Deployment

This site is hosted on **GitHub Pages** — a single `index.html` file, zero dependencies, no build step required.

### How to update

1. Edit `index.html` locally
2. Upload to the repo: **Add file → Upload files → Commit changes**
3. GitHub auto-rebuilds in ~1–2 minutes
4. Check progress under the **Actions** tab — green checkmark = live ✅


## 🛠️ How It Works

Everything runs in the browser — no backend, no APIs, no tracking.

- **Timezone math** uses the native [`Intl.DateTimeFormat`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat) API with IANA timezone identifiers, so DST (daylight saving time) is handled automatically for every region
- **Theme detection** reads `new Date().getHours()` from the visitor's local device — no location permissions needed
- **Converter** calculates the UTC equivalent of the input time, then renders it in every other timezone
- **Share string** always includes both AM/PM and 24H formats so it's readable for everyone

---

## 🧩 Adding a New Region

Find the `zones` array in the `<script>` section of `index.html` and add a new entry:

```javascript
{ flag: '🇯🇵', name: 'Japan', sub: 'Tokyo — Japan Standard Time', iana: 'Asia/Tokyo', label: 'JST (UTC+9)' },
```

That's it — the live clocks, converter, and share string pick it up automatically.

You can find the correct IANA identifier for any city at the [IANA Timezone Database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

---

## 🤖 Credits

This project was designed and built entirely through a conversation with **[Claude](https://claude.ai)** (Claude Sonnet, by [Anthropic](https://anthropic.com)) — including the UI design, timezone logic, AM/PM converter, light/dark theming, shareable output formatting, and this README.

No external libraries were used. Just one HTML file and a good AI collaborator. 🌸

---
