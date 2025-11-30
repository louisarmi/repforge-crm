# RepForge Frontend

This folder will contain the main Next.js application for RepForge.

The goal of the frontend is to give insurance agents and agency admins a clean, fast, and simple UI to:

- Run live AI sessions
- Upload and analyze recorded calls
- View AI-generated notes and scores
- Manage leads and clients in a CRM
- Let admins see agent activity

---

## Responsibilities

The frontend should handle:

- Authentication for:
  - Solo agents
  - Agency admins
- Dashboard:
  - Today’s follow-ups
  - Recent leads
  - Recent calls
- Live Session UI:
  - Start / End session button
  - Real-time transcript view
  - Live notes panel
  - Live extracted client details
- Upload Recording UI:
  - Audio file upload
  - Show processing state
  - Show transcript, notes, and scores
- CRM:
  - Leads list (search + filter)
  - Lead detail page (profile, notes, scores, transcripts, history)
  - Pipeline stage changes
- Admin views:
  - Agent list
  - Basic agent stats (calls, leads, averages)
  - Read-only access to leads/clients

---

## Planned Tech Stack

- Next.js (App Router)
- TypeScript
- Tailwind CSS
- Supabase client (Auth, Database, Storage)
- API calls to AI endpoints (OpenAI / Anthropic)
- Deployed to Vercel

---

## Local Development (High-Level)

1. Clone the repository
2. Enter the `frontend` folder
3. Install dependencies (npm / yarn / pnpm)
4. Run the dev server

Environment variables will come from the root `.env.example` and Supabase project setup.
