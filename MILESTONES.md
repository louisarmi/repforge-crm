# RepForge – V1 Milestones & Development Plan

This document outlines the official development milestones for RepForge V1.  
These milestones represent the minimum viable product (MVP) required for launch.

---

## 🟦 Milestone 1 — Project Setup  
**Timeline:** 2–3 days  
**Includes:**
- Next.js project creation (App Router, TypeScript)
- Supabase project setup (Auth + Postgres)
- File storage buckets for audio
- Basic folder structure
- Environment variables configured
- Simple landing page placeholder
- User sign-up / login working

**Deliverable:**  
Functional skeleton app deployed to Vercel (empty but running).

---

## 🟩 Milestone 2 — CRM Core + Lead Storage  
**Timeline:** 5–7 days  
**Includes:**
- Dashboard layout
- Add lead manually (name, phone, client notes)
- Auto-create lead from AI analysis
- Lead table (sort + filter)
- Lead detail page
- Call history tab inside each lead
- Supabase schemas for:
  - `users`
  - `leads`
  - `calls`
  - `notes`
  - `scores`
  - `followups`

**Deliverable:**  
CRM works standalone without AI or transcription.

---

## 🟧 Milestone 3 — AI Upload Mode  
**Timeline:** 5–7 days  
**Includes:**
- Upload audio file (MP3/M4A/WAV)
- Whisper/OpenAI/Claude transcription
- AI extraction (health, budget, medications, state, age, objections, goals)
- AI-generated notes
- Multi-dimensional lead scoring:
  - Sale likelihood
  - Suitability
  - Underwriting risk
  - Chargeback risk
  - Follow-up urgency
  - Rapport score
- Option: “Save to CRM” or “Discard”

**Deliverable:**  
AI upload mode fully functional end-to-end.

---

## 🟥 Milestone 4 — Live Session Mode  
**Timeline:** 5–7 days  
**Includes:**
- Real-time transcription
- Real-time note drafting
- Real-time extraction of key client info
- Auto-processing final analysis when call ends
- Simple “Start Session / End Session” UI
- Save Session → creates CRM entry

**Deliverable:**  
Live mode works in real time with streaming transcription.

---

## 🟪 Milestone 5 — Agency Admin Mode  
**Timeline:** 3–4 days  
**Includes:**
- Agency account
- Invite agents by email
- View agent activity:
  - Calls completed
  - Leads created
  - Average scores
- Read-only client profiles
- Basic billing integration prep (Stripe later)

**Deliverable:**  
Admin can oversee agents and read summaries.

---

## 🟫 Milestone 6 — Deployment & QA  
**Timeline:** 2–3 days  
**Includes:**
- Vercel deployment
- Supabase policies tightened (RLS)
- Test audio upload + live session
- Test CRM, lead creation, admin mode
- Bug fixing
- Production-ready handoff

---

# 🔥 Total Timeline  
**22–30 days depending on developer speed.**

---

# 🎯 Goal  
This development plan produces a **real, functioning AI insurance CRM** with:

- Live transcription  
- AI extraction  
- AI scoring  
- CRM auto-building  
- Admin dashboard  
- Upload recording processing  

Everything required for RepForge to launch a paid beta.
