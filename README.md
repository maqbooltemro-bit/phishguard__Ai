# PhishGuard AI 🛡️
### AI-Powered Phishing & Scam Detector

> Real-time detection of phishing emails, SMS scams, and malicious URLs using a custom ML classifier and RAG knowledge base — **zero external APIs, zero dependencies.**

---

## 🌐 Live Demo
**Deployment:** [https://maqbooltemro-bit.github.io/phishguard-ai](https://maqbooltemro-bit.github.io/phishguard-ai)

---

## 👥 Team Members

| Name | Roll No |
|------|---------|
| Member 1 | maqbool Ahmed 2k24/AI/44|
| Member 2 | Abdul wasie 2k24/AI/03 |

---

## 📋 Project Overview

**Domain:** Cybersecurity  
**Problem:** Pakistan and globally, phishing scams cause billions in losses yearly. Users receive fake bank alerts, prize SMS, fake job offers, and tax refund scams that steal credentials and money.

**Solution:** PhishGuard AI — A browser-based application that analyzes suspicious messages and URLs in real-time to detect phishing attempts before the user falls victim.

---

## 🤖 AI/ML Components

### 1. Custom ML Classifier (Rule-Based + Weighted Scoring)
- Analyzes text against **50+ features** organized into categories
- Each feature has a weighted score contribution
- Final 0-100 risk score with threshold-based classification:
  - **0-29:** Safe
  - **30-59:** Suspicious
  - **60-100:** Dangerous (Phishing)

### 2. RAG Knowledge Base (Retrieval-Augmented Generation)
Built-in knowledge base of known scam patterns specific to Pakistan and globally:

```
Categories:
- Urgency tactics (14 patterns)
- Threat language (13 patterns)
- Financial bait (15 patterns)
- Credential harvesting (12 patterns)
- Suspicious URL patterns (17 patterns)
- Legitimate signal markers (12 patterns)
```

### 3. URL Analysis Engine
- TLD reputation checking
- Brand impersonation detection (typosquatting)
- IP-based URL detection
- HTTP vs HTTPS verification
- Subdomain abuse detection
- Known safe domain whitelist

### 4. NLP Heuristics
- Exclamation mark density analysis
- Long number string detection (phone/account bait)
- Currency + money bait correlation
- Text length normalization

---

## 🚀 Features

- ✅ **Email / SMS Analysis** — Paste any suspicious message for instant analysis
- ✅ **URL Scanner** — Check any URL for phishing indicators
- ✅ **Scan History** — Track all previous analyses in the session
- ✅ **Example Presets** — 5 built-in examples (bank scam, prize scam, tax scam, job scam, legit email)
- ✅ **Risk Score Meter** — Visual 0-100 risk gauge
- ✅ **Indicator Breakdown** — Each red flag explained clearly
- ✅ **Educational Guidance** — Actionable advice for each result
- ✅ **Session Statistics** — Count of scanned, caught, and safe messages
- ✅ **Zero External APIs** — Runs 100% in the browser
- ✅ **No Installation** — Open index.html directly

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| ML Engine | Custom weighted classifier (JS) |
| Knowledge Base | RAG pattern database (embedded) |
| URL Analysis | Custom URL threat parser |
| Deployment | GitHub Pages (free, no server needed) |

---

## 📁 Project Structure

```
phishguard-ai/
├── index.html          # Complete application (single file)
├── README.md           # This file
└── screenshots/        # Demo screenshots (optional)
```

---

## 🚀 How to Deploy (GitHub Pages)

1. **Fork or create** this repository on GitHub
2. Go to **Settings → Pages**
3. Under "Source", select **Deploy from a branch**
4. Select **main branch** and **/ (root)** folder
5. Click **Save**
6. Your site will be live at `https://maqbooltemro-bit.github.io/phishguard-ai`

**That's it! No build step, no npm, no server required.**

---

## 💻 How to Run Locally

```bash
# Clone the repo
git clone https://github.com/maqbooltemro-bit/phishguard-ai.git

# Open in browser (no server needed)
cd phishguard-ai
open index.html
# OR double-click index.html in file explorer
```

---

## 🧪 Test Cases

| Input | Expected Result |
|-------|----------------|
| "Your HBL account suspended, verify now http://hbl-secure.tk" | HIGH RISK |
| "Congratulations! You won PKR 500,000, pay processing fee" | HIGH RISK |
| "FBR refund portal: http://fbr-refund.xyz — enter CNIC" | HIGH RISK |
| "Work from home, earn Rs. 80,000, pay registration fee" | SUSPICIOUS |
| "Your Daraz order #123 has been shipped" | LIKELY SAFE |

---

## 🔍 Algorithm Details

```
Risk Score Calculation:

score = 0
FOR each urgency phrase found: score += 15
FOR each threat phrase found:  score += 20
FOR each money bait found:     score += 12
FOR each credential request:   score += 25
FOR each suspicious URL:       score += 30
FOR each legitimate signal:    score -= 10
IF excessive exclamation marks: score += 10
IF long number strings:        score += 8

final_score = clamp(score, 0, 100)

verdict = "SAFE"       if score < 30
verdict = "SUSPICIOUS" if 30 <= score < 60
verdict = "PHISHING"   if score >= 60
```

---



## 🔗 Links

- **GitHub Repo:** https://github.com/maqbooltemro-bit/phishguard-ai
- **Live Demo:** https://maqbooltemro-bit.github.io/phishguard-ai
- **PTA Complaint Portal:** https://report.pta.gov.pk

---

## 📜 License

MIT License — Free to use for educational purposes.
