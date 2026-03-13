# 🧠 NeuroBeat — AI-Powered Music Therapy for Neurorehabilitation

**NeuroBeat** is a clinical-grade, AI-driven neurorehabilitation web app that uses personalized rhythmic beats and music to improve motor control, gait, speech, and fine motor recovery in **Parkinson's** and **stroke** patients.

> Built on the principle of **auditory-motor entrainment** — synchronizing movement to rhythm to bypass damaged neural pathways.

---

## ✨ Features

- **5 Therapy Modes** — Gait Training, Upper Limb Motor, Speech Rhythm, Melodic Intonation, Cognitive Rhythm
- **AI Beat Generation** — Powered by Hugging Face (`facebook/musicgen-small`) with Web Audio API fallback
- **Adaptive Feedback Loop** — Auto-adjusts BPM in real-time based on patient sync accuracy
- **Clinician Dashboard** — Create patients, set baselines, assign therapy, monitor progress
- **Patient Dashboard** — Start sessions, track personal progress with interactive charts
- **Baseline Assessments** — 8 assessment types (gait, tapping, speech, balance, coordination, cognitive, upper limb, melodic)
- **Progress Tracking** — 30-day trend visualizations for accuracy, BPM, and session history
- **5 Beat Sounds** — Metronome, Drum, Soft Bell, Wooden Block, Piano

---

## 🏗️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python 3.11+, Flask 3.1.2 |
| Database | SQLite via SQLAlchemy / Flask-SQLAlchemy |
| Frontend | Jinja2 Templates, Vanilla CSS, Vanilla JS |
| Audio AI | Hugging Face API + Web Audio API (client-side fallback) |
| Auth | Session-based (Werkzeug password hashing) |

---

## 📁 Project Structure

```
NEURO_BEATS/
├── app.py                  # Flask app factory & DB config
├── main.py                 # Entry point (port 5000)
├── models.py               # 6 SQLAlchemy models
├── routes.py               # 20+ Flask endpoints
├── beat_generator.py       # AI beat generation engine
├── migrate_db.py           # DB migration script
├── requirements.txt        # Pip dependencies
├── pyproject.toml          # Modern Python project config
├── instance/
│   └── neurobeat.db        # SQLite database
├── static/
│   ├── css/custom.css      # Application styles
│   └── js/
│       ├── audio.js        # Client-side audio synthesis
│       ├── charts.js       # Progress chart rendering
│       ├── session.js      # Therapy session logic
│       └── dropdown.js     # UI dropdown component
└── templates/              # 9 Jinja2 HTML templates
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.11 or higher
- pip or uv package manager

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/NEURO_BEATS.git
cd NEURO_BEATS

# Install dependencies
pip install -r requirements.txt

# Run the application
python main.py
```

The app will be available at **http://localhost:5000**

### Environment Variables (Optional)

| Variable | Description | Default |
|---|---|---|
| `SESSION_SECRET` | Flask session secret key | `neurobeat-secret-key-dev` |
| `DATABASE_URL` | Database connection URI | `sqlite:///neurobeat.db` |

---

## 🔄 How It Works — The Clinical Loop

```
1. Clinician registers → Creates patient accounts
2. Baseline Assessment → Measures cadence, tapping speed, speech rate
3. Personalized Prescription → Sets target BPM (e.g., 10% above baseline)
4. Therapy Session → Patient syncs movement to AI-generated beats
5. Adaptive Feedback → System auto-adjusts BPM in real-time
6. Progress Tracking → Charts show improvement trends over time
```

---

## 🗃️ Database Schema

| Table | Purpose |
|---|---|
| `users` | User accounts (patients & clinicians) |
| `patient_profiles` | Patient condition, baselines, stroke-specific data |
| `clinician_profiles` | License, specialization |
| `therapy_sessions` | Session logs with BPM, accuracy, metrics |
| `session_metrics` | Per-timestamp BPM and sync data |
| `baseline_assessments` | Clinical measurements and scores |

---

## 🎯 Therapy BPM Guidelines

| Session Type | Severe | Moderate | Mild |
|---|---|---|---|
| Gait Training | 40 BPM | 50 BPM | 60 BPM |
| Upper Limb / Cognitive | 45 BPM | 55 BPM | 65 BPM |
| Speech / Melodic | 50 BPM | 65 BPM | 80 BPM |

---

## 🤝 User Roles

### Clinician
- Register an account
- Create and manage patient profiles
- Conduct baseline assessments
- Monitor patient progress remotely

### Patient
- Log in with clinician-provided credentials
- Start therapy sessions across 5 modalities
- Receive real-time adaptive beat adjustments
- View personal progress charts

---

## 📄 License

This project is for educational and research purposes.

---

> ⚡ NeuroBeat — bridging AI, music, and clinical rehabilitation.
