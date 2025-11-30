# Contributing to RepForge

Thank you for your interest in contributing to RepForge.  
This document explains how developers should work inside the repository and maintain consistent quality.  
RepForge is currently in active development with a clearly defined roadmap.

---

## 📘 Before You Start

Please read these files first:

- README.md  
- MILESTONES.md  
- docs/V1_BLUEPRINT.md (when created)  
- frontend/README.md (when created)  

You should be familiar with:

- Next.js (App Router + TypeScript)  
- Supabase (Auth, Database, Storage)  
- AI APIs (OpenAI, Anthropic)  
- Audio upload/transcription handling  

If anything is unclear, ask before proceeding.

---

## 🧱 Project Structure

Project structure (no code block to avoid formatting issues):

repforge/  
• docs/  
• frontend/  
• .env.example  
• .gitignore  
• LICENSE  
• MILESTONES.md  
• README.md  
• CONTRIBUTING.md  

---

## 🔀 Contribution Workflow

### 1. Create a New Branch

Name branches clearly:

- feature/live-session  
- feature/upload-processing  
- fix/transcription-logic  
- docs/update-blueprint  

### 2. Make Focused Changes

Each pull request should address **one** feature or fix.  
Do not mix unrelated changes.

---

## 🧹 Code Style

- Use **TypeScript** everywhere  
- Use **Prettier** for formatting  
- Keep naming consistent:  
  - Components → ComponentName.tsx  
  - Hooks → useSomething.ts  
  - Utilities → something.ts  
  - API Routes → route.ts  

---

## 📝 Commit Messages

Use this format:

- feat: add live session streaming transcription  
- fix: correct lead extraction bug  
- chore: update environment example  
- docs: improve AI scoring documentation  
- refactor: simplify audio pipeline  

Avoid vague commits like “update” or “misc”.

---

## 🔐 Environment Variables

Do **not** commit `.env` files.  
Use `.env.example` to list required variables.

Never include:

- API keys  
- Supabase keys  
- Service role keys  
- Passwords  
- Tokens  

in any commits or PRs.

---

## 🧪 Running Locally

Inside `/frontend`:

1. Run `npm install`  
2. Run `npm run dev`

You must configure:

- Supabase project  
- Audio storage buckets  
- RLS policies  
- AI API keys  

Live features require microphone permissions.

---

## ✔ Pull Request Requirements

A PR must include:

- Summary of what changed  
- Why it changed  
- Testing instructions  
- Confirmation that no secrets were included  

PRs that break structure or include sensitive data will be closed.

---

## 💬 Communication

For help:

- Open a GitHub Issue  
- Email: support@repforgecrm.com  

---

## 🙏 Thank You

Your contributions help RepForge deliver a powerful AI-assisted CRM for insurance agents.  
We appreciate your support.
