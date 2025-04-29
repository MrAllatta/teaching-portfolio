---
layout: single
title: ATS-to-Remind Integration Tool
permalink: /tools/ats-remind/
sidebar:
  nav: "main"
author_profile: true
---

## ATS-to-Remind Import Tool

**Overview:**
This tool bridges NYC’s ATS (Automate The Schools) system with Remind’s messaging platform, enabling more effective, multilingual, and personalized communication between schools and families.

Remind is a powerful communication tool—but many of its more advanced features (multiple guardians, home-language targeting, class roster sync) are locked behind technical complexity. This tool solves that problem by making it easier to engineer and automate the required data feeds.

---

### Core Functions
- **Class Roster Sync:** Automatically matches class schedules from ATS with Remind rosters
- **Guardian Mapping:** Imports multiple contacts per student with custom tagging (e.g., math class only, advisory only)
- **Home Language Support:** Pulls language data from ATS to pre-segment recipients for translation or targeted messages
- **Conditional Logic:** Supports rule-based grouping (e.g., parent of student in both AP CS and Advisory)

---

### Technical Notes
- Built using spreadsheet transformation tools and custom scripts
- Requires basic CSV output from ATS and admin-level access to Remind
- Can be semi-automated, but full automation limited by DOE third-party software policies
- Used internally by school data and tech teams (not plug-and-play for general teacher use without setup)

---

### Impact
- Made Remind viable for **bilingual and multilingual parent communication**
- Reduced manual errors and teacher load around contact management
- Supported consistent messaging across programs, especially in high-variance classrooms

---

**Status:** Internal prototype in use from 2018–2021. Currently being reviewed for broader documentation and potential reuse. If interested in collaboration or viewing sample files, [please reach out via the Contact page](/contact/).

