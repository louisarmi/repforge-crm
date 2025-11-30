# RepForge Design – UI & Screen Layouts

This folder documents the planned UI and UX for RepForge V1.  
It is not code – it is a visual and layout guide for designers and frontend developers.

The design goal:  
**Simple, clean, no clutter. Built for speed while dialing and taking calls.**

---

## 🎨 General Style

- Modern, minimal SaaS look
- Light background, dark text
- Primary accent: blue
- Secondary accent: soft gray
- Clear section headers
- Cards for key blocks (leads, calls, stats)
- Everything must be readable while a call is happening

---

## 🖥 Main Screens (V1)

### 1. Login / Signup

**Elements:**
- Logo + app name (“RepForge”)
- Tabs: “Login” / “Create Account”
- Fields:
  - Email
  - Password
- Button: “Log In”
- Link: “Create an account” / “Forgot password”

**For admin sign-up:**
- Checkbox or toggle: “I am an agency owner / admin”

---

### 2. Agent Dashboard

**Top section:**
- Greeting: “Welcome back, [First name]”
- Quick stats (cards):
  - Follow-ups due today
  - New leads this week
  - Calls saved this week

**Middle section:**
- “Today’s Follow-Ups” list:
  - Client name
  - Follow-up reason
  - Due time
  - Button: “Open lead”

**Bottom:**
- Buttons:
  - “Start Live Session”
  - “Upload Call Recording”

---

### 3. Live Session Screen

Layout: **Three columns**

**Left column – Lead info (optional):**
- If attached to existing lead:
  - Name
  - Phone
  - Stage
  - Last contact date
- If new lead:
  - “New lead – info will populate after call”

**Center column – Transcript:**
- Live text area
- New lines appear in real time as the client/agent talk
- Scrollable if long

**Right column – AI Panel:**
- Section: “Live Notes”
  - Bullet list updated during call
- Section: “Detected Info”
  - Age (if known)
  - State
  - Smoker (yes/no)
  - Health flags
  - Budget
  - Existing coverage (if heard)

**Bottom bar:**
- Left: Timer (call/session duration)
- Center: Button – “End Session”
- Right: Status indicator – “Listening…”

After “End Session”, redirect to **Review Screen**.

---

### 4. Upload Recording Screen

Simple centered layout:

- Title: “Upload Call Recording”
- Card with:
  - File input (drag & drop or click)
  - Supported formats (MP3 / M4A / WAV)
  - Option: “Attach to existing lead” or “New lead”
- Button: “Upload & Analyze”
- After upload → show loading state: “Analyzing call…”

Then redirect to **Review Screen**.

---

### 5. Review Screen (After Live or Upload)

Card-based layout with sections:

**Top:**
- Lead name (or “New lead”)
- Option to select or change lead

**Left column:**
- Summary card:
  - Bullet summary of call
  - Key objections
  - Key commitments
- Follow-up card:
  - Recommended follow-up date
  - Reason
  - Quick button: “Add to follow-ups”

**Right column:**
- Scores card:
  - Sale Likelihood (0–100)
  - Suitability
  - Underwriting risk
  - Chargeback
  - Rapport
  - Follow-up urgency
- Transcript tab:
  - Full transcript
- Data tab:
  - Extracted fields (age, state, meds, budget, etc.)

**Bottom:**
- Primary button: “Save to CRM”
- Secondary button: “Discard”

---

### 6. Leads List (CRM)

Table view:

Columns:
- Name
- Phone
- Sale score
- Stage (pipeline)
- Last contact
- Next follow-up

Top right:
- Search bar (by name or phone)
- Filter dropdown:
  - Stage filter
  - Score filter (e.g. only >70)

Clicking a row opens **Lead Detail**.

---

### 7. Lead Detail

Layout: header + tabs

**Header:**
- Lead name
- Stage dropdown
- Primary button: “Start Live Session with this lead”

**Tabs:**
1. Overview:
   - Client info
   - Summary of last call
   - Top scores
2. Notes:
   - AI notes + manual notes
3. Calls:
   - List of past calls → click to open a call record
4. Scores:
   - Graph or list of scores over time
5. Data:
   - Extracted health, financial, and insurance data

---

### 8. Admin Dashboard

**Top stats:**
- Agents count
- Total calls this week
- New leads this week

**Agents table:**
- Agent name
- Email
- Calls this week
- Leads created
- Average sale score

Clicking an agent opens their subset of leads/read-only view.

---

## 🧪 Design Priorities

- Easy for an agent to use while on the phone
- No clutter
- Important things big and obvious:
  - “Start Live Session”
  - “Upload Recording”
  - “Save to CRM”
- Scores and notes easy to skim quickly

This document is the visual reference guide for designers and frontend developers.
