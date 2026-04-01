# 🟠 DPM Skills Profile Platform

> **Internal tool for Orange Business — Delivery Practice**  
> A fully browser-based platform for Delivery Project Managers to build structured skills profiles, and for managers to aggregate them into a live team analytics dashboard.

---

## 🚀 Live Site

**[→ Open Platform](https://ahmedwalid4499.github.io/orange-dpm-skills/)**

> No login required. No backend. No installation. Just open and use.

---

## 📌 What This Is

The DPM Skills Profile Platform solves a simple problem: within Orange Business, managers have no structured, consistent way to see what skills and certifications their team actually holds. This platform provides:

- A **guided wizard** for DPMs to build their own skills profiles in ~5 minutes
- A **Manager Dashboard** to upload team profiles and instantly get a visual team analytics report
- A **Certification Library** with 18 curated PM certifications and 15 data analytics courses
- A **Ask for Help** connector to reach colleagues across 3 clusters by email

Everything runs in a single HTML file. No server, no database, no IT setup required.

---

## ✨ Features

### For DPMs — CV / Skills Profile Builder

A clean 11-step wizard covering:

| Step | Content |
|------|---------|
| 1 | Basic info — name, role, summary, photo, APM Cluster |
| 2 | Education — degree, institution, dates |
| 3 | Languages — with proficiency level picker |
| 4 | Professional links — LinkedIn, GitHub, custom links |
| 5 | Certifications — 22 preloaded + custom |
| 6 | Tools & Platforms — 25 preloaded + custom |
| 7 | Professional Skills — 28 across 5 PM domains |
| 8 | Products & Services — 25 Orange Business products |
| 9 | Work Experience — jobs with bullet points |
| 10 | Custom Sections — free-form additional content |
| 11 | Template selection + Generate |

**Exports:**
- 📄 **Word Document** — branded `.docx` profile
- 📦 **JSON Profile** — structured data file for the Manager Dashboard (filename includes name + cluster)
- 🖨 **Print** — browser print dialog
- 📤 **Send to SharePoint** — downloads JSON and opens your SharePoint folder in one click

---

### For Managers — Team Dashboard

Upload your team's JSON profiles (or load a saved report bundle) to get:

| Section | Description |
|---------|-------------|
| KPI Strip | Team size, total certs, unique tools, products coverage |
| Top Certifications | Ranked list with visual frequency bars |
| Certification Distribution | Horizontal bar chart, top 10 |
| Tool Adoption | Horizontal bar chart, top 10 |
| Products & Services Coverage | Coloured bar chart, top 10 |
| Skill Gap Heatmap | Person × PM domain grid with colour coding |
| Team Member Table | Individual breakdown with cert count, tools, skills |
| Side-by-Side Comparison | Compare any two DPMs across all domains on a radar chart |
| Team Competency Radar | Average team scores across 5 PM domains |

**Three ways to load data:**

1. **Upload CV Profiles** — select `.json` files from the CV Builder
2. **Load Saved Report** — reload a previously exported team bundle JSON
3. **🏢 Current Team Dashboard** — instantly loads all 78 team members with their current certifications (hardcoded, editable in the source)

**Report actions:** 💾 Save Report · 📂 Load Report · ⬇ Export PDF · 🖨 Print

---

### Certification Library

18 curated PM certifications with:
- Provider logo, exam format, question count
- Price, estimated prep time, difficulty level
- Renewal requirements
- Direct link to official enrolment page

Filterable by domain: All · Agile · Risk & Governance · Technical · Business

Plus 15 **Data Analytics & Reporting** courses.

---

### Ask for Help

Search and email colleagues across 3 clusters:

| Cluster | Manager | Colour |
|---------|---------|--------|
| 🌍 N&S EU (Inc. Transversal) | Karim ElZarka / Peter Sabet | Orange |
| 🏔️ DACH (Inc. BASF) | Peter Sabet | Blue |
| 🌷 Benelux | Maryam Etry | Green |

Select one or more DPMs → pick a topic → write your message → one click opens Outlook with everything pre-filled.

---

## 🛠️ Technical Details

| Detail | Value |
|--------|-------|
| Format | Single self-contained `.html` file |
| Deployment | GitHub Pages (static hosting) |
| Backend | None |
| Authentication | None |
| Libraries | Chart.js 4.4.1, JSZip 3.10.1, Google Fonts |
| Fonts | Outfit (headings), DM Mono (mono/labels) |
| Browser storage | `localStorage` (profiles persist across sessions) |
| Themes | Light + Dark mode, toggled in header, persisted in `localStorage` |

### localStorage Keys

| Key | Purpose |
|-----|---------|
| `obTheme` | Light / dark mode preference |
| `ob_dpm_profiles_v1` | Cached manager dashboard profiles |
| `ob_sp_site_url` | SharePoint site URL (remembered) |

---

## 📂 File Structure

```
/
└── orange_cv_builder.html    ← The entire platform (single file)
└── README.md                 ← This file
```

That's it. The whole platform is one file.

---

## 🔧 Editing the Hardcoded Team Data

When a team member earns a new certification, open `orange_cv_builder.html` in any text editor, search for `HARDCODED_TEAM`, and update their `certs` array:

```js
// Find the person and edit their certs array:
{ name:'Ahmed Osama', certs:["PMP","ACP","PSM1","ITIL Foundation","MSC"] },

// To add a new cert, just append it:
{ name:'Ahmed Osama', certs:["PMP","ACP","PSM1","ITIL Foundation","MSC","Six Sigma"] },
```

**Available cert names** (must match exactly, case-sensitive):

```
"PMP"  "ACP"  "PSM1"  "PSPO1"  "Synergy Foundation"  "Synergy Practitioner"
"SCM"  "SAFE"  "ITIL Foundation"  "ITIL Strategist"  "MSC"  "Six Sigma"  "MBA"
```

### Adding a new tool or product

Search for `id="toolGrid"` or `id="productGrid"` in the file and add a new label:

```html
<label class="check-label"><input type="checkbox" value="New Tool Name"> New Tool Name</label>
```

---

## 📋 Preloaded Data

### Certifications (22 preloaded in wizard)
PMP · PRINCE2 · PRINCE2 Agile · PMI-ACP · PMI-RMP · PMI-PBA · CAPM · CSM · SAFe · AgilePM · ITIL v4 · TOGAF · CISSP · CompTIA Project+ · Six Sigma Green Belt · Six Sigma Black Belt · MSP · MoP · P3O · MoR · OKR Practitioner · Design Thinking

### Tools & Platforms (25 preloaded)
MS Project · Jira · Confluence · Smartsheet · Asana · Monday.com · Trello · Wrike · Notion · ServiceNow · SAP · Oracle · Salesforce · Power BI · Tableau · Excel Advanced · PowerPoint · SharePoint · Teams / Zoom · Miro / Mural · Azure DevOps · GitHub · Python · SQL · Primavera P6

### Products & Services (25 preloaded)
Fortinet · Palo Alto Networks · Cisco Devices · Unified Communications · LAN Devices · WAN / SD-WAN · MPLS Networks · Cloud Connectivity · Microsoft 365 · Microsoft Azure · AWS · Google Cloud · Managed Security Services · SOC / SIEM · Endpoint Security · Zero Trust Network Access · Contact Centre Solutions · Video Conferencing · IoT Solutions · Data Centre Services · Backup & Recovery · Network Monitoring · IP Telephony / VoIP · Business Internet · Digital Workplace

---

## 📤 Updating & Deploying

1. Edit `orange_cv_builder.html` directly in any text or code editor
2. Commit and push to the `main` branch
3. GitHub Pages auto-deploys — live within ~30 seconds

```bash
git add orange_cv_builder.html
git commit -m "Update: add new cert for [Name]"
git push
```

---

## 🔗 Related Internal Tools

| Tool | Link |
|------|------|
| FTE Calculator | [ahmedwalid4499.github.io/FTE-Calculator](https://ahmedwalid4499.github.io/FTE-Calculator/) |
| DPMs Portal *(under development)* | [ahmedwalid4499.github.io/dpms-portal](https://ahmedwalid4499.github.io/dpms-portal/) |

---

## 👤 Author

**Ahmed El-Bourgy**  
Delivery Project Manager — Orange Business, N&S EU (Inc. Transversal)  
[ahmed.elbourgy.ext@orange.com](mailto:ahmed.elbourgy.ext@orange.com)

---

## ⚠️ Internal Use Only

This platform is built exclusively for internal use within the Orange Business Delivery Practice. It contains no external-facing data and should not be shared outside the organisation. All profile data is processed entirely in the browser — nothing is sent to any server.

---

*© 2026 Ahmed El-Bourgy · All rights reserved*
