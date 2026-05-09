<div align="center">

# 💸 FinAnalyzer
### Smart UPI Financial Management — Built with ❤️ by [Vaishnavi Vadla](https://github.com/VaishnaviVadla33) & [Sowmya Maakam](https://github.com/Sowmyamaakam)

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-upi--finanalyzer.onrender.com-6C63FF?style=for-the-badge)](https://upi-finanalyzer.onrender.com/)
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-2.x-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![Firebase](https://img.shields.io/badge/Firebase-Firestore-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)

</div>

---

> **FinAnalyzer** transforms the chaos of UPI receipts into clarity. Upload a screenshot — our OCR engine handles the rest, giving you real-time dashboards, smart spending alerts, group expense splitting, and AI-powered savings suggestions. No manual entry. No guesswork.

---

## 👩‍💻 About the Team

This project was designed and built end-to-end by two developers:

| | Developer | GitHub |
|---|---|---|
| 🎯 | **Vaishnavi Vadla** | [@VaishnaviVadla33](https://github.com/VaishnaviVadla33) |
| 🚀 | **Sowmya Maakam** | [@Sowmyamaakam](https://github.com/Sowmyamaakam) |

---

## ✨ What Makes FinAnalyzer Different

```
📸 Snap → 🔍 Scan → 📊 Analyze → 💡 Save
```

No more spreadsheets. No more manual logging. Just upload your UPI receipt screenshot and get instant financial intelligence.

---

## 🔑 Core Features

### 🧠 Smart OCR Scanning
- Auto-extracts **amount**, **payee**, **date**, and **type** from UPI screenshots
- Supports Google Pay, PhonePe, Paytm, and more
- Bulk upload — process up to **10 receipts at once**
- Advanced preprocessing pipeline for high accuracy

### 📊 Comprehensive Dashboard
- Real-time income, expense & balance overview
- Monthly savings goal with progress tracker
- Spending alerts when limits are crossed
- Clean visual summary of your financial health

### 📈 Advanced Analytics
- Interactive spending trend charts (monthly & yearly)
- Category-wise expense breakdown
- Peak spending time analysis
- **AI-powered savings suggestions** based on your habits
- Cash flow insights

### 👥 Group Expense Management
- Create groups for shared expenses (trips, rent, events)
- Invite members via **email** or **invite code**
- Role-based access: Admin / Member / Viewer
- Group-level analytics and contribution tracking

### 🔔 Smart Alerts & Goals
- Set monthly savings targets
- Category-specific spending alerts
- Email notifications for budget reports
- Customizable thresholds per time period

### 🔒 Security First
- Firebase Authentication (email/password)
- PBKDF2 password hashing with salt
- Session timeout management
- Input validation & sanitization
- HTTPS enforced in production

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Backend** | Flask (Python 3.8+) |
| **Database** | Firebase Firestore |
| **Auth** | Firebase Authentication |
| **OCR** | Tesseract OCR + custom preprocessing |
| **Data** | Pandas, NumPy |
| **Email** | Gmail SMTP |
| **Frontend** | HTML5, CSS3, JavaScript (ES6+) |
| **Charts** | Chart.js |
| **Deployment** | Render + Docker |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Tesseract OCR
- Firebase project (Firestore + Auth enabled)
- Gmail account with App Password

### 1. Clone the Repository

```bash
git clone https://github.com/VaishnaviVadla33/upi-finanalyzer.git
cd upi-finanalyzer
```

### 2. Set Up Virtual Environment

```bash
# macOS / Linux
python3 -m venv venv && source venv/bin/activate

# Windows
python -m venv venv && venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Install Tesseract OCR

```bash
# macOS
brew install tesseract

# Ubuntu / Debian
sudo apt-get update && sudo apt-get install tesseract-ocr

# Windows — download from:
# https://github.com/UB-Mannheim/tesseract/wiki
```

### 5. Firebase Setup

1. Go to [Firebase Console](https://console.firebase.google.com/) → Create project
2. Enable **Authentication** (Email/Password)
3. Enable **Firestore Database**
4. Project Settings → Service Accounts → **Generate New Private Key**
5. Save as `FIREBASE_CREDENTIALS.json` in the project root

### 6. Environment Variables

Create a `.env` file in the project root:

```env
# Firebase Admin SDK
FIREBASE_KEY_PATH=FIREBASE_CREDENTIALS.json

# Firebase Client Config (Project Settings → General)
FIREBASE_API_KEY=your_api_key_here
FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
FIREBASE_DATABASE_URL=https://your-project-default-rtdb.firebaseio.com
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_STORAGE_BUCKET=your-project.appspot.com
FIREBASE_MESSAGING_SENDER_ID=123456789012
FIREBASE_APP_ID=1:123456789012:web:abc123def456
FIREBASE_MEASUREMENT_ID=G-XXXXXXXXXX

# Gmail SMTP
SENDER_EMAIL=your-email@gmail.com
SENDER_APP_PASSWORD=your-16-char-app-password
```

> **Gmail App Password**: Enable 2FA → Google Account Security → App Passwords → Generate for "Mail"

### 7. Run Locally

```bash
python app.py
# App runs at http://localhost:5000
```

---

## 🐳 Docker

```bash
# Build & run with Compose
docker-compose up --build

# Or with Docker directly
docker build -t finanalyzer .
docker run -p 5000:5000 --env-file .env finanalyzer
```

---

## ☁️ Deploy to Render

1. Fork this repo to your GitHub
2. Create a **Web Service** on [Render](https://render.com/)
3. Connect your repo → set branch to `deployment`
4. Add all `.env` variables in Render's Environment section
5. Add `FIREBASE_CREDENTIALS.json` as a secret file at `/etc/secrets/FIREBASE_CREDENTIALS.json`
6. Deploy — auto-redeploys on every push 🎉

---

## 📱 Usage Guide

### First Time Setup
1. Sign up at `/auth`
2. Set your monthly savings goal in **Settings**
3. Upload your first UPI receipt via **OCR Scan**
4. Watch your dashboard populate automatically

### Bulk Upload Flow
1. Go to **OCR Scan** → Click **Bulk Upload**
2. Select up to 10 screenshots
3. Review extracted data (edit if needed)
4. Save all at once

### Group Expenses
1. **Groups** → Create New Group
2. Add members by email or share the invite code
3. Track contributions and view group analytics

---

## 📁 Project Structure

```
finanalyzer/
├── app.py                    # Main Flask application
├── dashboard_helpers.py      # Analytics & utility functions
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── render.yaml
├── templates/
│   ├── base.html
│   ├── index.html            # Landing page
│   ├── auth.html             # Login / Register
│   ├── dashboard.html        # Main dashboard
│   ├── upload.html           # Single receipt upload
│   ├── upload_multiple.html  # Bulk upload
│   ├── analytics.html
│   ├── history.html
│   ├── group.html
│   ├── group_dashboard.html
│   └── settings.html
└── static/
    ├── css/main.css
    └── js/main.js
```

---

## 🔌 API Reference

<details>
<summary><strong>Authentication</strong></summary>

| Method | Endpoint | Description |
|---|---|---|
| POST | `/login` | User login |
| POST | `/register` | User registration |
| POST | `/api/forgot-password` | Request password reset |
| GET | `/logout` | Logout |

</details>

<details>
<summary><strong>Transactions</strong></summary>

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/upload` | Upload & OCR process receipt |
| POST | `/api/save-transaction` | Save single transaction |
| POST | `/api/save-transactions-bulk` | Save multiple transactions |
| GET | `/api/transactions` | Get all transactions |
| PUT | `/api/transaction/<id>` | Update transaction |
| DELETE | `/api/transaction/<id>` | Delete transaction |

</details>

<details>
<summary><strong>Dashboard & Analytics</strong></summary>

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/dashboard-data` | Dashboard summary |
| GET | `/api/analytics-data` | Detailed analytics |
| GET | `/api/spending-categories` | Category breakdown |
| GET | `/api/dashboard-alerts` | Active alerts & savings progress |

</details>

<details>
<summary><strong>Groups</strong></summary>

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/groups` | All user groups |
| POST | `/api/create-group` | Create new group |
| POST | `/api/join-group` | Join via invite code |
| GET | `/api/group-analytics/<id>` | Group analytics |

</details>

---

## 🧪 OCR Processing Pipeline

```
Image Input
    ↓
Grayscale Conversion
    ↓
Contrast Enhancement
    ↓
Noise Reduction
    ↓
Tesseract Text Extraction
    ↓
₹ Symbol Normalization (handles OCR misreads)
    ↓
Context-aware Amount Extraction
    ↓
Name Cleaning (removes emojis, artifacts, phone numbers)
    ↓
Auto Category Classification
    ↓
Structured Transaction Object
```

**Supported Apps:** PhonePe (more in progress)  
**Supported Formats:** PNG, JPG, WEBP

---

## 🐛 Troubleshooting

| Issue | Fix |
|---|---|
| `Tesseract not found` | Install Tesseract and add it to system PATH |
| `Firebase connection failed` | Check `FIREBASE_CREDENTIALS.json` path and validity |
| `OCR inaccurate` | Use clear, well-lit, non-blurry screenshots |
| `Email not working` | Verify Gmail App Password + 2FA enabled |
| `Port 5000 in use` | Change port in `app.py` or kill the conflicting process |

**Enable debug mode:**
```python
if __name__ == '__main__':
    app.run(debug=True, port=5000)
```

---

## 🔐 Security Highlights

- All secrets stored in environment variables — never hardcoded
- Firebase credentials excluded from version control
- PBKDF2 + salt for password hashing
- Session tokens expire on inactivity
- Full input validation on all endpoints
- HTTPS enforced in production
- CORS configured for API routes

---

## ⚡ Performance Notes

- Transaction data cached for fast dashboard loads
- Firestore queries optimized with field-level indexing
- Images processed asynchronously (non-blocking)
- Static assets minified for production builds

---

<div align="center">

### Built with passion by

**[Vaishnavi Vadla](https://github.com/VaishnaviVadla33)** &nbsp;•&nbsp; **[Sowmya Maakam](https://github.com/Sowmyamaakam)**

*Making personal finance effortless, one UPI receipt at a time.*

⭐ If you found this useful, please star the repo!

</div>
