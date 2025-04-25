---
title: "Behind the Systems: Tools, Logic, and Automation"
layout: default
permalink: /systems/
---
## ATS → Remind Integration System  
**Overview:**  
Brief summary of what it does and why it's valuable.

**Technical Design:**
- **Data Sources:** ATS exports (.csv), DOE ID mappings, teacher rosters.
- **Key Sheets and Scripts:**
  - `"guardian_merge.csv"`: Cleaned export with deduplicated guardian contacts.
  - `"group_assignments"`: Cross-referenced teacher-section mapping.
  - Scripts using Google Sheets formulas: `QUERY`, `FILTER`, `ARRAYFORMULA`, `REGEXMATCH`.
- **Automations:**
  - Step-by-step of how it loads, cleans, merges, and outputs data.
  - Use of Google Apps Script (if any) for automation or email triggers.
- **Equity Features:**
  - Home language logic, fallback conditions, tiered messaging priority.
- **Screenshots or live demo snippets** (scrubbed for privacy).
- **Downloadable template or sandbox file** (optional).

---

## Jumprope → Dashboard & Planning Suite  
**Overview:**  
Why this tool was built and what it replaces/enhances.

**Data Design:**
- **Raw Inputs:** Jumprope exports (`standards.csv`, `students.csv`, etc.)
- **Outputs:** Dashboards by teacher, grade, and student group.
- **System Architecture:** 
  - Master planner → live slave sheets for advisory and subject teams.
  - Use of `IMPORTRANGE`, `VLOOKUP`, `SPARKLINE`, `IFERROR`, and `HYPERLINK`.
- **Automations:**
  - Periodic update triggers, “rollover” logic between semesters.
- **Team Workflow:**
  - Who uses what, when, and how it's handed off.
- **Equity Lens:**
  - Supports IEP flagging, Regents alerts, ENL service tracking.
- **Annotated templates or copies** with dummy data.

---

