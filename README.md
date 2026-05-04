# Akanksha Sharma — Portfolio Site

Single-file static portfolio + 6 downloadable Excel files + resume PDF. Drop the whole folder into Vercel.

## What's in here

```
/
├── index.html                                       ← the site
├── README.md                                        ← this file
└── files/
    ├── akanksha-sharma-resume.pdf                   (91 KB)
    ├── cross-industry-financial-analysis.xlsx      (22 KB)
    ├── kpi-dashboard.xlsx                           (105 KB)
    ├── vba-pivot-auto-refresh.xlsx                  (464 KB)
    ├── three-statement-source-model.xlsx            (528 KB)
    ├── revenue-recognition-framework.xlsx           (9 KB)
    └── waterfall-business-cases.xlsx                (10 KB)
```

The HTML references files via `files/...` relative paths, so the folder must stay together when you deploy.

## What's on the site

**10 hobby projects**, three of them interactive:

1. **Cross-Industry Analysis** (featured) — Five-industry benchmarking model: Infrastructure (Primoris), Technology (Microsoft), Healthcare (J&J), Financial Services (JPMorgan), Utilities (NextEra). Revenue trajectories FY20–FY24 + scenario projections. *Download.*
2. **Interactive KPI Dashboard** — Toggle between Revenue / Profit / Cash and watch the bars and active KPI card swap live. *Download.*
3. **VBA Pivot Auto-Refresh** — Shows the actual `Workbook_Open()` macro that walks every sheet refreshing every PivotTable. *Download.*
4. **Sales Target Planning** — Quarterly bookings consolidation. *Methodology badge (client data confidential).*
5. **Q1 Achievement vs Xactly** — SAP / Xactly variance reconciliation. *Methodology badge.*
6. **T&E Concentration** — Pareto analysis: 7% of headcount, 29% of spend. *Methodology badge.*
7. **Service Line Revenue** — 4,990-row monthly cadence by practice. *Methodology badge.*
8. **Three-Statement Source Model** — Chart of accounts + 5,015 transactions. *Download.*
9. **Revenue Recognition Framework** — FPP / T&M / SOW decision logic. *Download.*
10. **Waterfall Charts** (featured) — Four interactive FP&A business cases: YoY Profit Development, Profit by Company with subtotal, Cash Flow, and Actual vs PY March 2025 YTD. *Download.*

**Sections:** Hero · Selected Work (with category filter) · Experience (Co-Founder, Coforge, Wipro) · Education (Stevens MS '25, Graphic Era B.Com '15) · Contact.

## Why 6 of 10 projects download and 4 show a methodology badge

Of the original ten data sources, four contained real client/employee names from former employers (Wipro/Coforge). Even after running automated anonymization, Excel pivot caches and hidden references can retain original data — verifying an .xlsx is fully scrubbed is genuinely difficult. Publishing those files would risk leaking former-employer data and put you on the wrong side of an NDA.

The "Methodology available on request" framing actually plays *better* in finance recruiting. It signals: *I built this work, I can walk you through every line in an interview, and I don't put confidential data on the public internet.* That's exactly the data-handling instinct hiring managers want.

The 6 downloadable files are clean by construction: public-company data, synthetic data, generic accounting structure, or original FP&A frameworks.

---

## Deploy to Vercel

**Drag & drop (no GitHub needed)**

1. Zip the folder containing `index.html`, `README.md`, and the `files/` subfolder.
2. Go to https://vercel.com/new → sign in → "Add New → Project".
3. Drag the unzipped folder in (or click Browse).
4. Click Deploy. ~30 seconds to live URL.

**Via GitHub (cleaner long-term)**

1. Create a new GitHub repo, push the whole folder to it (preserving structure).
2. On Vercel: Add New → Project → Import from your repo → Deploy.
3. Future edits: push to GitHub, Vercel auto-redeploys.

**Custom domain:** Vercel project settings → Domains → add your domain → follow DNS instructions.

---

## Editing the site

It's one HTML file. No build step, no framework, no dependencies beyond Google Fonts (Fraunces, Geist, JetBrains Mono).

- **Add a project:** copy any `<article class="project reveal">...</article>` block, paste, edit. `data-cat` controls the filter pill it belongs to: `strategy`, `dashboard`, `planning`, `variance`, `cost`, or `model`.
- **Change colors:** edit the `:root` CSS variables at the top of `<style>`.
- **Swap a card's badge:** replace the `<a class="dl-link">` block with `<span class="methodology-badge">` (or vice versa) at the bottom of any project card.
- **Interactive widgets:** the KPI Dashboard and Waterfall projects use `data-interactive="kpi"` / `data-interactive="waterfall"` on the `.project` element, with `.kpi-tab[data-metric=…]` / `.wf-tab[data-case=…]` controls. Toggling shows/hides `.kpi-view-{metric}` / `.wf-view-{case}` SVG groups. JS lives in the `<script>` block at the bottom.

---

Built fresh, no template. If anything breaks in your browser, ping me.
