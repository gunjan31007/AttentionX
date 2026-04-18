# ⚡ AttentionX — Automated Content Repurposing Engine

> Turn a 60-minute lecture into 7 viral short-form clips — automatically.

[![Demo Video](https://img.shields.io/badge/Demo-Watch%20Now-c8f03e?style=for-the-badge)](https://drive.google.com/drive/folders/14Ho_iQ4btbK81gCsTXzcN93p7UusZBKf)


---

## 🎯 Problem

Mentors, educators, and creators produce hours of high-value long-form content. But modern audiences consume in 60-second bursts. Valuable "golden nuggets" of wisdom are buried in 60-minute videos — inaccessible to most viewers.

**AttentionX** solves this with a fully automated AI pipeline that extracts, crops, and captions your best moments.

---

## 🚀 Features

| Feature | Technology |
|---|---|
| 🎙️ **Audio Transcription** | OpenAI Whisper — word-level timestamps |
| 📈 **Emotional Peak Detection** | Librosa RMS energy analysis |
| 🧠 **AI Moment Selection** | Claude Sonnet — viral potential scoring |
| 👁️ **Smart Face Tracking** | MediaPipe face detection for vertical crop |
| 📱 **Vertical Crop (9:16)** | FFmpeg smart reframe for TikTok/Reels |
| ✍️ **Dynamic Captions** | FFmpeg drawtext — karaoke-style overlays |
| 🔗 **URL Support** | yt-dlp — YouTube & direct video URLs |

---

## 🏗️ Architecture

```
User Upload / URL
       ↓
  FFmpeg Extract Audio
       ↓
  Whisper Transcription (word timestamps)
       ↓
  Librosa Energy Analysis (detect peaks)
       ↓
  Claude AI Analysis (find viral moments)
       ↓
  FFmpeg Clip Extraction + MediaPipe Crop
       ↓
  FFmpeg Caption Overlay (hook + title)
       ↓
  Download Ready Clips ✅
```

---

## 📦 Tech Stack

**Backend**
- Python 3.10+
- FastAPI + Uvicorn
- OpenAI Whisper (speech-to-text)
- Librosa (audio energy analysis)
- MediaPipe (face detection)
- MoviePy / FFmpeg (video processing)
- yt-dlp (URL video download)
- Anthropic Claude API (AI moment selection)

**Frontend**
- Vanilla HTML/CSS/JS
- Custom cursor animations
- Magnetic button effects
- Scroll-triggered reveals
- Real-time processing steps UI

---

## ⚡ Quick Start

### 1. Clone the repo
```bash
git clone https://github.com/gunjan31007/attentionx.git
cd attentionx
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```
```

### 4. Run the server
```bash
cd backend
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

### 5. Open the app
```
http://localhost:8000
```

---

## 🎬 How It Works

### Step 1 — Upload or paste URL
Drop any MP4/MOV/AVI/MKV/WebM or paste a YouTube link. Configure clip duration, number of clips, and output format.

### Step 2 — AI Processing Pipeline
1. **Transcription**: Whisper converts audio to timestamped text
2. **Energy Analysis**: Librosa finds where the speaker is most animated
3. **AI Selection**: Claude analyzes the transcript and scores each moment for viral potential, emotional impact, and sentiment
4. **Smart Crop**: FFmpeg reframes to 9:16 vertical (MediaPipe tracks the face in production)
5. **Caption Overlay**: Hook headline + clip title burned in with high-contrast styling

### Step 3 — Download Your Clips
Each clip comes with:
- Viral score, emotion score, sentiment score
- Auto-generated hook headline
- Karaoke-style captions
- One-click download

---

## 📡 API Reference

| Endpoint | Method | Description |
|---|---|---|
| `/api/health` | GET | Health check |
| `/api/upload` | POST | Upload video file |
| `/api/upload-url` | POST | Process from URL |
| `/api/status/{job_id}` | GET | Poll processing status |
| `/api/clips/{job_id}` | GET | Get completed clips |
| `/api/download/{job_id}/{clip_index}` | GET | Download a clip |

Full interactive docs: `http://localhost:8000/api/docs`

---

## 🎥 Demo Video

> **[▶ Watch the full demo here](https://drive.google.com/drive/folders/14Ho_iQ4btbK81gCsTXzcN93p7UusZBKf)**

---

## 📊 Evaluation Criteria Coverage

| Criteria | How We Address It |
|---|---|
| **Impact (20%)** | Fully functional pipeline: transcribe → AI analyze → crop → caption |
| **Innovation (20%)** | Combines Whisper + Librosa + Claude + MediaPipe in one seamless flow |
| **Technical Execution (20%)** | Clean FastAPI backend, async processing, real-time status polling |
| **User Experience (25%)** | Stunning dark UI, custom cursor, magnetic buttons, scroll animations |
| **Presentation (15%)** | Demo video + hosted app link in README |

---

## 🌐 Deployment

The app can be deployed on **Railway**, **Render**, or **fly.io**:

```bash
# Example: Railway
railway login
railway init
railway up
```

---

## 👤 Author

Built for the **AttentionX AI Hackathon** by UnsaidTalks — April 2026

---

## 📄 License

MIT
