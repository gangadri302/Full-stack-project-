# PhishGuard — Phishing Email & Website Detector

Full-stack defensive cybersecurity project.

## Architecture

User → Web UI → Flask API → Hybrid Detection Engine → Risk Report

The backend combines:
- rule/feature analysis for email and URLs
- optional VirusTotal URL reputation lookup
- optional Google Web Risk URL lookup
- optional TF-IDF + Logistic Regression text model

## Run locally

### 1. Backend

```bash
cd backend
python -m venv .venv
# Windows: .venv\\Scripts\\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt

# Optional: copy .env.example to .env and add reputation API keys
python app.py
```

The API runs at `http://127.0.0.1:5000`.

### 2. Frontend

Open `index.html` in a browser after the backend is running.

The frontend sends scans to:
`http://127.0.0.1:5000/api/analyze`

For deployment, use a secure HTTPS backend URL and update `API_BASE` in `index.html`.

## ML model

The included training CSV is only a tiny demonstration dataset. Do not claim production accuracy from it. Replace it with a properly labeled dataset and evaluate on held-out data before reporting metrics.

## GitHub

Upload the contents of this folder to a GitHub repository. Do not commit `.env`, API keys, or generated ML model files containing sensitive material.
