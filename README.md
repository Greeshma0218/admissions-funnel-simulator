# 🎓 Admissions Funnel Simulator

> An interactive, browser-based tool that reverse-engineers your enrollment pipeline — from enrollment goal to top-of-funnel inquiry need — using configurable yield rates and what-if analysis.

**Live demo →** [your-username.github.io/admissions-funnel-simulator](https://your-username.github.io/admissions-funnel-simulator)

---

## Why this exists

Every admissions team talks about enrollment funnels. Almost no one has a fast, interactive way to answer the question:

> *"If I want to enroll 400 students and my deposit yield drops 5%, how many more inquiries do I need?"*

This tool answers that question in real time — no spreadsheet, no SQL, no waiting on a report.

---

## Features

- **Enrollment goal input** — set your target class size and the entire funnel recalculates instantly
- **4 configurable yield rates** — Inquiry → App → Admit → Deposit → Enroll
- **What-if mode** — adjust a scenario in parallel and see exactly how each stage shifts (green/red delta badges)
- **College presets** — one-click benchmarks for Small Liberal Arts, Mid-size University, Highly Selective, and Transfer-heavy institutions
- **Insight summary** — auto-generated plain-English takeaway identifying your bottleneck stage
- **Bar chart** — visual breakdown with overlay in what-if mode
- **No backend, no login, no data leaves your browser** — pure HTML/CSS/JS

---

## Tech stack

| Layer | Technology |
|-------|-----------|
| UI | Vanilla HTML + CSS (no framework) |
| Charts | Chart.js 4.4 |
| Fonts | Google Fonts — Inter + Space Grotesk |
| Hosting | GitHub Pages |
| Dependencies | Zero npm packages |

---

## Getting started

### Option 1 — Open locally
```bash
git clone https://github.com/YOUR-USERNAME/admissions-funnel-simulator.git
cd admissions-funnel-simulator
open index.html   # or double-click it in Finder/Explorer
```

### Option 2 — GitHub Pages (free hosting)
1. Fork this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your simulator is live at `https://YOUR-USERNAME.github.io/admissions-funnel-simulator`

---

## How the math works

The simulator works backwards from your enrollment goal:

```
Enrolled  = Goal
Deposited = ceil(Enrolled  / deposit_yield)
Admitted  = ceil(Deposited / admit_yield)
Applied   = ceil(Admitted  / app_yield)
Inquiries = ceil(Applied   / inquiry_yield)
```

All values round up (`ceil`) because you can't admit half a student.

---

## College presets

| Preset | Goal | Inq→App | App→Admit | Admit→Dep | Dep→Enroll |
|--------|------|---------|-----------|-----------|------------|
| Small liberal arts | 350 | 18% | 70% | 30% | 93% |
| Mid-size university | 1,200 | 25% | 60% | 26% | 90% |
| Highly selective | 500 | 12% | 18% | 42% | 96% |
| Transfer-heavy | 600 | 35% | 72% | 38% | 88% |

Presets are illustrative benchmarks, not official NACAC data.

---

## Built by

**Greeshma** — Business Systems Analyst in Enrollment Management, Slate CRM admin, Power BI developer, and data science graduate student.

This project is part of a portfolio of open-source higher ed analytics tools. If you work in admissions operations or enrollment management and find this useful, feel free to fork it, adapt it, or reach out.

---

## Contributing

Pull requests are welcome. Ideas for future versions:
- [ ] Export funnel to PDF/image
- [ ] Save and compare multiple named scenarios
- [ ] NACAC benchmark data overlay
- [ ] Multi-year trend view

---

## License

MIT — free to use, adapt, and share.
