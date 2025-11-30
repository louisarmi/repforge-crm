# RepForge AI Pipeline

This folder documents the AI logic, prompts, scoring rules, extraction fields, and analysis workflow used by RepForge.  
These prompts and rules define how the AI interprets calls, creates summaries, and scores leads.

The AI pipeline is the core of RepForge’s intelligence.

---

# 🧠 Overview of the AI Pipeline

RepForge uses a multi-phase AI system:

1. **Transcription**  
2. **Extraction**  
3. **Notes Generation**  
4. **Scoring (6 dimensions)**  
5. **Follow-Up Recommendation**

These phases run for both:
- **Live Session Mode** (with continuous updates)  
- **Upload Recording Mode**

---

# 🎤 Phase 1 — Transcription

RepForge uses Whisper/OpenAI for:
- Accurate paragraph-level transcription  
- Detecting key phrases  
- Detecting filler words  
- Detecting “underwriting signals” (red flags)
- Timestamped transcript (optional in V1)

Output is plain text transcript used in later steps.

---

# 📄 Phase 2 — Extraction (Field Detection)

AI identifies and extracts:

**Client Identity**
- First name  
- Age or age range  
- State of residence  

**Financial**
- Budget  
- Income indicators  
- Affordability comments  

**Health**
- Current conditions  
- Medical history  
- Prescriptions  
- Tobacco usage  
- Height / weight (if stated)

**Insurance**
- Existing coverage  
- Carrier if mentioned  
- Gaps in coverage  
- Motivation for new coverage  

**Behavioral**
- Objections  
- Pain points  
- Buying signals  
- Authority / decision-maker status  

This extraction builds the CRM client profile.

---

# 📝 Phase 3 — AI Notes

AI generates a clean, agent-ready summary with:

- Overview of the conversation  
- Client goals  
- Key objections  
- Needs & motivations  
- Underwriting concerns  
- Action items  
- Suggested script angle for next call  

The notes must be:
- Clear  
- Bullet-point formatted  
- No filler language  
- No assumptions  
- No hallucinated information  

---

# 📊 Phase 4 — Lead Scoring (Six-Dimensional)

Each call produces **6 separate 0–100 scores**:

### 1. **Sale Likelihood Score**
Measures:
- Buying signals  
- Engagement  
- Financial readiness  
- Tone + willingness  

### 2. **Suitability Score**
Measures:
- Whether insurance is appropriate  
- Budget match  
- Product fit  

### 3. **Underwriting Risk Score**
Measures:
- Medical risk  
- Prescription conflicts  
- Tobacco status  
- Carriers likely to decline  

### 4. **Chargeback Risk Score**
Measures:
- Hesitation  
- Commitment level  
- Red flags for lapses  
- “I need to think about it” behaviors  

### 5. **Rapport & Trust Score**
Measures:
- Tone  
- Cooperation  
- Relationship building  
- Positive sentiment  

### 6. **Follow-Up Urgency Score**
Measures:
- How soon the agent should call back  
- Based on timing signals  
- Based on opportunity risk  

---

# 📅 Phase 5 — Follow-Up Recommendation

AI outputs:

- Follow-up date  
- Follow-up explanation  
- Suggested script angle  
- “Reason for next contact”  

Example:  
“Follow up in 2 days — client showed strong interest but needed to check bank account draft date.”

---

# 🏗 Live Mode Prompts vs Upload Mode Prompts

The system has **two prompt sets**:

### **Live Mode**
- Must output partial notes  
- Must update extracted fields live  
- Must NOT finalize scores until call ends

### **Upload Mode**
- Runs full analysis at once  
- No intermediate outputs  
- Produces complete notes, scores, and fields  

Both modes end with the same final analysis prompt.

---

# 🧩 Model Selection

Recommended default models:

- **Whisper (OpenAI)** → transcription  
- **GPT-4o-mini / Claude 3.5 Sonnet** → analysis  

Fallback models possible if needed.

---

# 🎯 Purpose of This Folder

This folder is NOT code —  
It contains the AI rules that developers must follow to implement consistent behavior.

Actual prompt files (JSON or text) will be added during development.
