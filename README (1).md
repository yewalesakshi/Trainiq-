<div align="center">

# ⚡ TrainIQ
### Faculty Training & Performance Management System

[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![No Backend](https://img.shields.io/badge/Backend-None%20Required-green)](https://github.com)
[![Works Offline](https://img.shields.io/badge/Works-Offline-blue)](https://github.com)

**A complete web-based faculty performance management system with ML-based classification algorithm, automated email notifications, Trello-style Kanban board, and promotion recommendations — all in a single HTML file.**

[📸 Screenshots](#-screenshots) · [🚀 Quick Start](#-quick-start) · [🧠 Algorithm](#-algorithm) · [🐛 Report Bug](../../issues)

</div>

---

## 📋 Table of Contents
- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Screenshots](#-screenshots)
- [Quick Start](#-quick-start)
- [Demo Accounts](#-demo-accounts)
- [Project Structure](#-project-structure)
- [Algorithm](#-algorithm)
- [Email Setup](#-email-setup)
- [Future Improvements](#-future-improvements)
- [License](#-license)
- [Author](#-author)

---

## 🎯 About

TrainIQ is a **Faculty Training and Performance Management System** built for educational institutions. It enables HODs (Head of Departments) to assign training tasks, track faculty progress, classify performance using a weighted ML algorithm, and automatically recommend promotions — all without any backend server or installation.

### 🔑 Problem Statement
> Most colleges track faculty performance manually using Excel sheets. There is no automated system to classify faculty or recommend promotions based on data. **TrainIQ solves this** by providing a digital platform with automated classification, real-time email notifications, and data-driven promotion recommendations.

---

## ✨ Features

### 👤 Authentication & User Management
- ✅ Secure login and registration system
- ✅ Role-based access — **Admin (HOD)** and **Faculty** roles
- ✅ Add, edit, delete, promote, demote, deactivate users
- ✅ All registered users visible on login page
- ✅ Persistent sessions using LocalStorage

### 📋 Task Management (Trello-Style)
- ✅ Admin assigns tasks with title, priority, due date, notes
- ✅ **Kanban Board** with 3 columns — Pending, In Progress, Completed
- ✅ Drag-free task movement between columns
- ✅ Reopen completed tasks back to Pending

### 📧 Email Notifications
- ✅ Auto email when task is assigned (includes notes & due date)
- ✅ Auto email when task is completed
- ✅ Both admin and faculty receive email alerts
- ✅ Complete email history log (From / To / Time / Task)
- ✅ Gmail API integration — zero backend required

### 📊 Faculty Performance Report
- ✅ **ML Classification Algorithm** — grades faculty A+, A, B, C
- ✅ **Weighted Scoring** — Completion(40%) + OnTime(30%) + Feedback(30%)
- ✅ Semester-wise performance table per faculty
- ✅ Visual progress bars with color-coded grades
- ✅ **Promotion Recommendation Engine**
- ✅ **PDF Report Download** for official records

### 🏠 Admin Dashboard
- ✅ Summary stats — Total, Completed, In Progress, Pending
- ✅ Click any faculty → view all assigned tasks instantly
- ✅ Real-time notification system
- ✅ Export all data as JSON
- ✅ Full data reset option

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **HTML5** | Application structure |
| **CSS3** | Styling, animations, responsive design |
| **Vanilla JavaScript** | Business logic & interactivity |
| **LocalStorage API** | Persistent data storage (no database) |
| **Gmail API** | Automated email notifications |
| **Blob API** | PDF report generation & download |
| **Web3Forms** | Form submission service |
| **Classification Algorithm** | Faculty grading & promotion logic |

---

## 📸 Screenshots

> Add screenshots of your app here after uploading

| Login Page | Admin Dashboard |
|---|---|
| ![Login](screenshots/login.png) | ![Dashboard](screenshots/dashboard.png) |

| Kanban Board | Faculty Report |
|---|---|
| ![Kanban](screenshots/kanban.png) | ![Report](screenshots/report.png) |

---

## 🚀 Quick Start

### No Installation Required!

**Option 1 — Direct Open:**
```bash
# Download index.html and double-click it
# Works in any browser — Chrome, Firefox, Edge
```

**Option 2 — Clone and Open:**
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/trainiq.git

# Navigate to folder
cd trainiq

# Open in browser
start index.html        # Windows
open index.html         # Mac
xdg-open index.html     # Linux
```

**Option 3 — GitHub Pages (Live Demo):**
```
Visit: https://YOUR_USERNAME.github.io/trainiq
```

---

## 👤 Demo Accounts

| Role | Email | Password |
|---|---|---|
| **Admin / HOD** | admin@trainiq.com | admin123 |
| **Faculty** | faculty@trainiq.com | user123 |

> ⚠️ Note: You can register your own accounts directly from the app.

---

## 📁 Project Structure

```
trainiq/
│
├── 📄 index.html          # Complete application (HTML + CSS + JS)
│                          # Contains all features in single file
│
├── 📄 README.md           # Project documentation
├── 📄 .gitignore          # Git ignore rules  
├── 📄 LICENSE             # MIT License
│
└── 📁 screenshots/        # Application screenshots
    ├── login.png
    ├── dashboard.png
    ├── kanban.png
    └── report.png
```

---

## 🧠 Algorithm

### Classification Algorithm (Decision Tree Based)

Our system uses a **Rule-Based Classification Algorithm** similar to a Decision Tree Classifier. It analyzes multiple weighted performance metrics to classify each faculty member.

```
╔══════════════════════════════════════════════════════╗
║           PERFORMANCE SCORE FORMULA                  ║
║                                                      ║
║  Score = (C × 0.4) + (O × 0.3) + (F × 0.3)         ║
║                                                      ║
║  Where:                                              ║
║    C = Task Completion Rate  → Weight: 40%           ║
║    O = On-Time Delivery Rate → Weight: 30%           ║
║    F = Feedback Score        → Weight: 30%           ║
╚══════════════════════════════════════════════════════╝

Classification Output:
┌──────────────┬────────────┬──────────────────────────────┐
│    Score     │   Grade    │   Promotion Recommendation   │
├──────────────┼────────────┼──────────────────────────────┤
│   ≥ 90%      │  A+ Excel  │  ⭐ Strongly Recommended     │
│   ≥ 75%      │  A  Good   │  👍 Eligible for Promotion   │
│   ≥ 60%      │  B  Avg    │  📋 Monitor Next Semester    │
│   < 60%      │  C  Poor   │  ⚠️ Performance Plan Needed  │
└──────────────┴────────────┴──────────────────────────────┘
```

### Example Calculation:
```
Faculty: Dr. Sharma
────────────────────────────────────
Task Completion  = 9/10  = 90%
On-Time Rate     = 8/10  = 80%
Feedback Score   = 4.2/5 = 84%

Score = (90 × 0.4) + (80 × 0.3) + (84 × 0.3)
      = 36 + 24 + 25.2
      = 85.2%

Result → Grade A (Good) → 👍 Eligible for Promotion
```

### Recommendation System (Content-Based Filtering):
```
Rule 1: Score ≥ 85 AND Feedback ≥ 4.0  →  ⭐ Strongly Recommend
Rule 2: Score ≥ 75 AND Feedback ≥ 3.5  →  👍 Eligible
Rule 3: Score ≥ 60                      →  📋 Monitor
Rule 4: Score < 60                      →  ⚠️ Not Recommended
```

---

## 📧 Email Setup

TrainIQ uses Gmail API for email notifications. Setup takes 2 minutes:

### Step 1 — Get Free Access Key
```
1. Go to web3forms.com
2. Enter your email address
3. Click "Create Access Key"
4. Copy the key from your inbox
```

### Step 2 — Configure in App
```
1. Login as Admin
2. Go to SMTP Settings (sidebar)
3. Paste your Access Key
4. Enter your admin email
5. Click "Save & Activate"
6. Click "Test Email" to verify
```

### Email Triggers:
| Trigger | Recipients |
|---|---|
| Task Assigned | Faculty Member |
| Task Completed | Faculty + Admin |
| Test Button | Admin |

---

## 🔮 Future Improvements

- [ ] Node.js + Express backend
- [ ] MongoDB database for cloud storage
- [ ] JWT authentication for production
- [ ] K-Nearest Neighbors (KNN) classification
- [ ] Random Forest for improved accuracy
- [ ] Linear Regression for performance prediction
- [ ] React.js frontend migration
- [ ] Mobile app (React Native)
- [ ] Department-wise analytics dashboard
- [ ] Student feedback integration module
- [ ] Multi-institution / multi-college support
- [ ] REST API for third-party integrations

---

## 📄 License

```
MIT License

Copyright (c) 2026 Sakshi Yewale

Permission is hereby granted, free of charge, to any person obtaining 
a copy of this software to use, copy, modify, merge, publish, and 
distribute it freely.
```

See [LICENSE](LICENSE) for full details.

---

## 👩‍💻 Author

<div align="center">

### Sakshi Yewale

*Computer Science Student | Web Developer | ML Enthusiast*

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/YOUR_USERNAME)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR_USERNAME)
[![Email](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:yewalesakshi1406@gmail.com)

</div>

---

<div align="center">

### ⭐ Star this repository if it helped you!

*Made with ❤️ by Sakshi Yewale*

**TrainIQ — Empowering Educational Institutions with Smart Faculty Management**

</div>
