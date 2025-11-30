# RepForge Backend

The backend for RepForge is built using **Next.js Server Actions + API Routes**, and integrates directly with **Supabase** for auth, database, and audio storage.  
This folder documents all backend logic and explains how the system should be structured.

There is no separate Express or Node server in V1 — the backend runs inside Next.js on Vercel.

---

# 🧠 Backend Responsibilities

The backend is responsible for:

- User authentication (via Supabase)
- Agency + agent creation workflows
- Lead creation and updates
- Audio upload handling (live + recording upload)
- Transcription pipeline (Whisper / OpenAI)
- AI analysis pipeline (Claude / GPT)
- Multi-score generation (sale, risk, chargeback, rapport, urgency)
- CRM data storage
- Follow-up scheduling
- Admin dashboards (read-only)

---

# 🗂 Route Structure (Planned)

Routes will live inside `/app/api/` in Next.js:

- `/api/auth/*`  
- `/api/leads/*`  
- `/api/calls/*`  
- `/api/transcribe/*`  
- `/api/analyze/*`  
- `/api/score/*`  
- `/api/admin/*`

This README simply documents the architecture so future developers know how to implement it.

---

# 📦 Supabase Schema (V1)

The backend must create and manage these Postgres tables:

- `users`
- `agencies`
- `agents`
- `leads`
- `calls`
- `notes`
- `scores`
- `followups`

Along with proper RLS (Row-Level Security) so:

- Agents can only see their own data  
- Admins can see their agents’ data  
- No one can see or edit anyone else’s CRM  

---

# 🔊 Audio Processing Flow (Critical)

### **Upload Mode**
1. User uploads audio file  
2. File saved to Supabase Storage  
3. Backend sends file to transcription API  
4. Backend sends transcript → AI analysis  
5. Backend saves notes, data, and scores  
6. Lead is created (if saved)

### **Live Session Mode**
1. Browser streams microphone audio chunks  
2. Backend receives streaming chunks  
3. Sends chunks to Whisper streaming endpoint  
4. Sends partial transcript → AI for live updates  
5. On “End Session”:  
   - Backend runs full analysis  
   - Generates final notes + scores  
   - Saves CRM entry

---

# 🤖 AI Pipeline (V1)

### Step 1 — Transcription  
Whisper / OpenAI transcription with punctuation + timestamps.

### Step 2 — Extraction  
AI identifies:
- Personal info  
- Budget  
- Medications  
- Coverage history  
- Goals & needs  
- Objections  

### Step 3 — Notes  
Clean agent-ready summary.

### Step 4 — Score Generation  
Six separate 0–100 scores:
- Sale Likelihood  
- Suitability  
- Underwriting Risk  
- Chargeback Risk  
- Rapport Score  
- Follow-Up Urgency  

### Step 5 — Follow-Up Recommendation  
AI outputs:
- Follow-up date  
- Reason  
- Reminder note  

---

# 🚀 Deployment

Backend is deployed automatically with the frontend via **Vercel**.  
Supabase handles:
- Database  
- Auth  
- Storage  
- Policies  

---

# 📌 Purpose of This Folder

This folder is NOT code —  
It is documentation that tells developers **how the backend must be architected**.

Actual backend logic will be implemented inside the Next.js `app` directory.

