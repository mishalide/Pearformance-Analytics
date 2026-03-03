# Scouting Dashboard MoSCoW Document

## Data Sources

- **Google Sheets Spreadsheet ID:**  
  `1H7iXtqda-3dN-CPAm2M9gk-XMtoxSoTGJhUSQ3aInXQ`

- **Match Data Sheet** (GID: `1072945473`)
- **Schedule Sheet** (GID: `923446952`)

---

## Tech Stack

- **Backend / Cache:** Supabase (PostgreSQL + Realtime)
- **Frontend Framework:** Palantir Blueprint
- **Data Source:** Google Sheets (Public CSV export)

---

# MoSCoW Requirements

---

## 🟥 Must Have (M)

### M1 — Data Ingestion from Google Sheets

- Fetch **Match Data** sheet via Google Sheets CSV export URL  
- Fetch **Schedule** sheet via CSV export URL  
- Parse and validate CSV rows into typed data structures  
- Handle malformed or missing rows gracefully without crashing  

### M2 — Supabase Backend & Caching

- Store ingested match and schedule data in Supabase tables  
- Implement a cache-first read strategy to reduce repeated Sheet fetches  
- Provide a manual or timed refresh mechanism to pull fresh data  
- Expose Supabase data to the frontend via the JS client library  

### M3 — Match Data Display

- Display important metrics regarding teams (e.g., average score, climb percentages)  
- Support basic filtering  

### M4 — Schedule Display

- Display the team-specific match schedule  

---

## 🟧 Should Have (S)

### S1 — Per-Team Aggregated Stats

- Calculate and display aggregate statistics per team (average score, consistency, auto vs teleop breakdown)  
- Show a team summary card  

### S2 — Data Export

- Allow export of currently displayed/filtered data as CSV  

### S3 — Realtime

- Use Supabase Realtime updates so the UI refreshes automatically when data is upserted  

### S4 — OAuth

- Restricted access (for Pearadox’s eyes only)

---

## 🟨 Could Have (C)

### C1 — Notes

- Allow drive team to add freeform notes to a team record  

### C2 — TBA Integration

- Cross-reference teams and match data against The Blue Alliance (TBA) API for OPR/DPR/CCWM stats  
- Link team numbers to their TBA profile pages  

### C3 — Statbotics Integration

- Integrate Statbotics for additional advanced statistics  

### C4 — Natural Language Processing

- Use NLP to assign a sentiment score to super scout data  

---

## ⬜ Won’t Have (W)

### W1 — Multi-Event Support

- literally why

### W2 — Native Mobile App

- Drive team carries a laptop; data is harder to read on mobile  

### W3 — Video Storage

- why??  

---

## Notes

- Verify and document column schema  
- Decide on refresh interval strategy  
