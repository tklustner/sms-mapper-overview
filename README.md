# sms-mapper-overview

SMS field reporting pipeline: free-text SMS → structured data → live map

## Overview

<img width="1440" height="719" alt="v2_clipped_sms_mapper_gif" src="https://github.com/user-attachments/assets/7c281da1-12c3-4c40-be3d-a41485ece8cb" />

Built for communities to document what's happening on the ground in real-time. Anyone with basic handset access can send a plain SMS. The system extracts structured signals, resolves the location, and the report lands on a live coordinator map within seconds.

No smartphone, data plan, or app installation required.

## How it works

SMS → Africa's Talking gateway → ingest → parse → score → resolve → map

Each stage is a discrete pipeline step with a full audit trail. Reports are 
confidence-scored (0.0–1.0) based on location match, date extraction, and signal 
density. Low-confidence reports automatically surfaced for human review.

## Features

- Rule-based NLP extracts case counts, symptom clusters, supply constraints, 
  and location references with zero LLM or inference API dependencies
- Synonym-aware parsing via coordinator-managed CSV RulePack (supports local 
  language variants)
- Offline-resilient relay queue survives server outages without changing CHW workflow
- PII programmatically scrubbed before storage; data stays on local hardware or African-jurisdiction VPS end-to-end
- Event-sourced domain model with SQLite read projection enables auditable schema migrations

## Stack

Python 3.12 / Flask · SQLite · React/Vite · Africa's Talking

## Status

Active development. Codebase private pending pilot deployment.  
[Concept Note →](sms_mapper_concept_note.pdf)
