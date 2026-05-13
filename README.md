# sms-mapper-overview

SMS field reporting pipeline: free-text SMS → structured data → live map

## Overview

<img width="1200" height="599" alt="sms_mapper_gif" src="https://github.com/user-attachments/assets/21b9343e-9eba-4ad4-8264-44b7e4b787da" />

Built for disease surveillance in low-resource settings. A community health worker
sends a plain SMS from any basic handset; the system extracts structured signals,
resolves the location, and surfaces the report on a live coordinator map within seconds.

No smartphone, data plan, or app installation required on the CHW side.

## How it works

SMS → Africa's Talking gateway → ingest → parse → score → resolve → map

Each stage is a discrete pipeline step with a full audit trail. Reports are 
confidence-scored (0.0–1.0) based on location match, date extraction, and signal 
density; low-confidence reports surface for human review.

## Features

- Rule-based NLP extracts case counts, symptom clusters, supply constraints, 
  and location references — no LLM, no inference API
- Synonym-aware parsing via coordinator-managed CSV RulePack (supports local 
  language variants)
- Offline-resilient: relay queue survives server outages without changing CHW workflow
- PII scrubbed before storage; data stays on local hardware or African-jurisdiction VPS
- Event-sourced domain model with SQLite read projection; schema migrations are 
  safe and auditable

## Stack

Python 3.12 / Flask · SQLite · React/Vite · Africa's Talking

## Status

Active development. Codebase private pending pilot deployment.  
[Concept Note →](sms_mapper_concept_note.pdf)
