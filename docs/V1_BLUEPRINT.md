# RepForge V1 – Full Product Blueprint

This blueprint defines the full feature scope and technical requirements for RepForge V1.  
This version focuses on **AI call processing**, **real-time transcription**, and a **lightweight CRM** for insurance agents and agencies.

---

# 🧩 Overview

RepForge V1 provides two core workflows:

1. **Live Session Mode**  
   - Agent presses “Start Session”  
   - AI listens in real time  
   - Transcription updates live  
   - Notes update live  
   - Key client info is extracted live  
   - When the call ends → Full AI analysis + scores  
   - Agent can **Save to CRM** or **Discard**

2. **Upload Recording Mode**  
   - Agent uploads MP3/M4A/WAV  
   - AI transcribes  
   - AI extracts client info  
   - AI scores the lead  
   - Agent chooses **Save to CRM** or **Discard**

Both methods feed into a personal CRM that stores lead/client profiles, transcripts, summaries, notes, scores, and follow-ups.

---

# 🎛 Live Session Mode (Real-Time)

### **Features**
- Start Session / End Session button  
- Microphone permission request  
- Real-time streaming transcription  
- Real-time note generation (updated continuously)  
- Real-time extraction of:  
  - Name  
  - Age  
  - State  
  - Health conditions  
  - Medications  
  - Budget  
  - Existing insurance  
  - Objections  
- Final post-processing at “End Session”  
- Option to save as a CRM client  
  
### **Tech Requirements**
- WebRTC microphone stream  
- Send audio chunks to backend  
- Use Whisper/OpenAI/Claude for streaming transcription  
- Use OpenAI/Claude for real-time field extraction  
- On “End Session”, run a final full analysis

---

# 📂 Upload Recording Mode

### **Features**
- Upload audio file  
- Automatic transcription  
- Automatic notes  
- Full AI extraction of client info  
- Full AI scoring  
- “Save to CRM” or “Discard”

### **Tech Requirements**
- Supabase Storage for audio  
- Whisper/OpenAI transcription API  
- Claude/OpenAI analysis prompts

---

# 🧠 AI Intelligence Engine

## Extracted Client Data (All Automatic)
- Full name (if stated)
- Age range
- State of residence
- Budget
- Income indicators
- Health profile
- Prescriptions
- Past insurance coverage
- Decision drivers
- Objections
- Urgency signals

## AI Notes Output
- Clean bullet summary  
- Needs & goals  
- Objections  
- Action items  
- Suggested follow-up  

## Multi-Dimensional Scoring
Each call generates:

1. **Sale Likelihood Score (0–100)**
2. **Product Suitability Score (0–100)**
3. **Underwriting Risk Score (0–100)**
4. **Chargeback Risk Score (0–100)**
5. **Rapport & Trust Score (0–100)**
6. **Follow-Up Urgency Score (0–100)**

---

# 📌 CRM System (V1)

### **Lead Profile Contains:**
- Basic contact info  
- Extracted client data  
- All call transcripts  
- AI notes  
- AI scores  
- Tasks / follow-ups  
- Pipeline stage  
- Last contacted date  
- Next follow-up date  

### **Lead Table**
- Name  
- Phone  
- Score (sale likelihood)  
- Stage  
- Last call  
- Next follow-up  

### **Lead Detail View**
Tabs:
1. Overview  
2. Notes  
3. Scores  
4. Transcripts  
5. Call History  

---

# 🏢 Agency Admin Mode (V1)

### **Admin Can:**
- Invite agents via email  
- View agent list  
- See:
  - Total calls  
  - Average scores  
  - Leads created  
- View agent client profiles (read-only)

### **Admin Cannot (in V1):**
- Edit agent clients  
- Modify transcripts  
- Change lead ownership  

---

# 🛠 Technical Stack (V1)

### **Frontend**
- Next.js App Router  
- TailwindCSS  
- TypeScript  

### **Backend**
- Next.js server actions  
- API routes as needed  
- Supabase Edge Functions (optional for audio)

### **Database (Supabase Postgres)**
Tables:
- users  
- agencies  
- agents  
- leads  
- calls  
- notes  
- scores  
- followups  

### **AI Providers**
- Whisper (transcription)  
- OpenAI GPT-4o-mini OR Claude 3.5 (analysis)

### **Storage**
- Supabase Storage buckets for audio files

### **Deployment**
- Vercel (frontend + backend)  
- Supabase (database + auth + storage)

---

# 🚀 V1 Success Criteria

RepForge V1 is complete when:

- Live Session mode works with real-time transcription  
- Upload Recording mode works  
- AI extracts all required fields  
- AI scoring works  
- Leads can be saved to CRM  
- CRM views function correctly  
- Admin mode works  
- Everything is deployed and stable

---

# 🎯 V1 Goal

A fully working AI-assisted CRM for insurance agents that automates call processing and builds client files automatically.
