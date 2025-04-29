---
layout: single
title: "Grade Converter Tool"
permalink: /tools/grade-converter/
sidebar:
  nav: "main"
author_profile: true
---

## Overview

The **Grade Converter** was a lightweight but powerful spreadsheet-based tool designed to bridge the gap between mastery-based grading systems and traditional transcript/report card platforms. 

At AFSE (Academy for Software Engineering), we piloted a move to mastery-based learning, but NYC Department of Education systems (STARS) still required traditional numeric grades. This tool automated the tedious work of translating fine-grained skill mastery data into clean, policy-compliant final grades.

## Features

- **Skill Aggregation**: Pulled individual mastery scores across multiple skills and units into an overall course score.
- **Flexible Weighting**: Allowed departments to adjust skill weights as mastery expectations evolved.
- **Transcript Conversion**: Mapped mastery levels onto required DOE numeric grading scales (e.g., 0–100 scale) transparently and fairly.
- **Auditability**: Embedded student-level grade justifications in case of parent, counselor, or administrative review.
- **Error Reduction**: Minimized human transcription errors compared to manual re-entry from separate mastery systems.
- **Speed**: Converted full course rosters in minutes, not days.

## Evidence of Impact

- Used across multiple CS and Math courses with thousands of grade records processed.
- Supported fairer, clearer grading in an unscreened, mastery-driven school environment.
- Enabled smoother conversations with families by maintaining transparency from mastery assessments to official grades.
- Provided the backbone data for summer course recovery programs during pandemic disruptions.

## Related Systems

The Grade Converter Tool was part of a larger suite of **internal dashboards and mail merge systems**:

- [Schoolwide Dashboards]({{ '/tools/dashboard/' | relative_url }}): Monitored attendance, engagement, grading, and interventions.
- [Mastery Rubric Alignment]({{ '/case-studies/mastery-rubric/' | relative_url }}): Supported the clarity and consistency of grading inputs.

## Screenshots (Coming Soon)
- Main grade conversion sheet
- Sample student-level audit sheet

## Notes for Future Development

- A more portable, shareable version of the Grade Converter could be built in Google Apps Script or lightweight web-based form.
- Could be adapted to integrate directly with future mastery-based SIS platforms.

> **Built for teachers, by a teacher — because spreadsheets should work *for* us, not the other way around.**

---

[Return to Tools Overview]({{ '/tools' | relative_url }})
