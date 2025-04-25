---
title: "Behind the Systems: Tools, Logic, and Automation"
layout: default
permalink: /tools/
---
## Instructional Tools & Systems

Behind every good classroom is a quiet stack of systems doing invisible work—streamlining logistics, reducing teacher friction, and keeping learning humane. This section highlights internal tools I built or adapted to support communication, grading, and instruction.

### Guiding Principles
- **Teacher-Centered Design** – Tools built to save time, not add complexity
- **Invisible Infrastructure** – Systems that quietly empower consistency
- **Data With Purpose** – Only tracking what supports student growth or teacher insight

### Featured Systems:
- [ATS-to-Remind Integration Tool](/tools/ats-remind/)
- [Grade Converter for Mastery-Based Uploads](/tools/grade-converter/)
- [Coming Soon: Progress Tracker Dashboard, Assignment Generator, Advisory Toolkit]

These aren’t polished products—they’re pragmatic tools born from need, iteration, and the belief that when the system works, teachers can focus on teaching.



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
  - Use of `IMPORTRANGE`, `INDEX MATCH`, `FILTER`, `QUERY`,  `SPARKLINE`, `IFERROR`, and `JOIN`.
- **Automations:**
  - Periodic update triggers, “rollover” logic between semesters.
- **Team Workflow:**
  - Who uses what, when, and how it's handed off.
- **Equity Lens:**
  - Supports IEP flagging, Regents alerts, ENL service tracking.
- **Annotated templates or copies** with dummy data.

---

