# RepForge – Real-Time AI Call Assistant & CRM for Insurance Agents  
Website: https://repforgecrm.com  
Support: support@repforgecrm.com

RepForge is an AI-powered call assistant and personal CRM designed for insurance agents and small agencies. It works alongside ANY dialer or phone system — no dialer integration required.

Agents simply:

- Start a **Live AI Session** (real-time transcription + live notes), or  
- Upload **recorded calls** for instant AI processing  

RepForge automatically handles:

- Full call transcription  
- Extraction of health data, budget, medications, coverage history  
- Structured call notes and summaries  
- Multi-dimensional AI scoring (sale likelihood, suitability, underwriting risk, chargeback risk, rapport, urgency)  
- Follow-up recommendations  
- Auto-building client files and CRM entries

Agencies can purchase seats for their team and access a light **admin dashboard** showing agent performance, call summaries, and client records (read-only in V1).

---

## 🚀 Core Features (V1)

### 🔊 Live Session Mode (Real-Time AI)
- Streaming transcription while the agent speaks  
- Live-updating notes panel  
- Live extraction of client fields (age, state, health issues, budget, prescriptions, etc.)  
- Final AI pass when the call ends for accuracy  

### 📁 Upload Recording Mode
- Upload MP3 / WAV / M4A  
- Instant transcript + AI analysis  
- Save to CRM or discard  

### 🧠 AI Intelligence Engine

#### Extracted Client Data
- Identity/demographics  
- Health profile & prescriptions  
- Budget  
- Existing coverage & gaps  
- Objections, goals, and decision drivers  

#### Multi-Dimensional Lead Scoring
1. **Sale Likelihood Score**  
2. **Product Suitability Score**  
3. **Underwriting Risk Score (NTO/Decline)**  
4. **Chargeback Risk Score**  
5. **Follow-Up Urgency Score**  
6. **Rapport & Relationship Score**

#### AI-Generated Notes
- Clean bullet-point summary  
- Key objections  
- Key commitments  
- “Next step” for the agent  
- Recommended follow-up window  

### 👤 Insurance-Specific CRM
- Client profiles auto-created from calls  
- Full call history  
- Notes, summaries, transcripts  
- Pipeline stages  
- “Follow-ups due today” dashboard  

### 🏛 Agency Admin Dashboard
- Invite agents  
- View agent call volume  
- See agent clients & activity  
- Read-only access to client profiles  

---

## 🧩 Architecture Overview

Planned stack:

- **Frontend:** Next.js (App Router), Tailwind, TypeScript  
- **Backend:** Next.js API Routes / Server Actions  
- **Auth & Database:** Supabase (Postgres + Auth)  
- **Storage:** Supabase Storage for audio  
- **AI Providers:** Whisper (transcription), OpenAI / Claude for analysis  
- **Hosting:** Vercel  
- **Domain:** https://repforgecrm.com  

---

## 📘 Documentation

Planned key docs:

- `docs/V1_BLUEPRINT.md` – full functional & technical blueprint  
- `MILESTONES.md` – development phases and deliverables  
- `frontend/README.md` – frontend setup notes  

---

## 📞 Contact

**Founder:** Louis Armitage  
**Support:** support@repforgecrm.com  
**Website:** https://repforgecrm.com
