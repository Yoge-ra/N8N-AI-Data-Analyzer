# 🛡️ AI Privacy Analyzer Workflow for n8n

An automated workflow powered by n8n and local LLMs (with Ollama) to analyze Google Sheet records for **PII (Personally Identifiable Information)** and **privacy risks**. This privacy-first solution provides daily data analysis summaries directly to Slack—completely local, self-hosted, and secure.

---

## 🚀 What It Does

This workflow helps your organization detect and handle privacy risks by analyzing structured data like HR records, user surveys, or internal documents.

- ⏰ **Runs once daily** (configurable)
- 📄 **Reads rows from Google Sheets** (hosted on your Google Drive)
- 🧠 **Uses Ollama (LLM)** to analyze each row
- 💡 **Detects sensitive fields (name, email, phone, etc.)**
- 🎯 **Assigns privacy risk levels** using emojis
- 📬 **Sends a privacy report to Slack**

---

## 🧱 Workflow Overview

[🕒 Daily Trigger] - Trigger to execute the flow daily once
↓
[📊 Read Google Sheet] - go to my google sheet and read the every data n it row by row
↓
[🔁 Split in Batches] - spliting each and every row as 1 per loop
↓
[🤖 Analyze via Ollama] - Locall installed ollama along with ngrok used data privacy
↓
[📨 Post to Slack] - Used to send final report at end


---

## 📂 Input Data Format

For Example Google Sheet should include columns like:

| Name       | Email              | Phone        | Notes                              |
|------------|--------------------|--------------|------------------------------------|
| Alice King | alice@example.com  | 555-123-4567 | Onboarding record - sensitive info |

> 📝 For our practice or testing, use my dummy data sheet file.

---

## ⚙️ Setup Instructions

### 1️⃣ Import the Workflow
- Open [n8n](https://n8n.io)
- Click **Workflows** → **Import**
- Upload the `AI Privacy Analyzer.json` file in this repository

### 2️⃣ Configure Each Node
| Node               | What to Update                                   |
|--------------------|--------------------------------------------------|
| 🕒 Trigger          | Set your preferred daily time                    |
| 📄 Google Sheet     | Enter your spreadsheet ID and range              |
| 🤖 Ollama           | Set your desired local model name (e.g., llama3) |
| 📢 Slack            | Set your Slack channel ID or name               |

### 3️⃣ Add Your Credentials
- **Google Sheets**: Service Account key
- **Slack**: Bot token with write message permissions
- **Ollama**: Local instance must be running with selected model

### 4️⃣ Test Run
- Temporarily swap **“Schedule Trigger”** for a **“Manual Trigger”** node
- Execute workflow and verify output in Slack

### 5️⃣ Activate Workflow
- Set back to Cron/Schedule trigger
- Click **"Activate"** in n8n

---

## 🔐 Privacy & Security First

- ✅ No cloud-based LLMs used
- ✅ Ollama runs locally, offline or air-gapped
- ✅ GitHub connection is *not* used for sensitive data
- ✅ Great for regulated industries: healthcare, HR, legal, finance


---

## 🔧 Optional Improvements

Want to extend the workflow?

- ➕ Append results back to the Google Sheet
- 📁 Store analysis reports in Drive, S3, or Dropbox
- 📬 Send scheduled digest emails (weekly compliance summary)
- 🔍 Add filters to only flag high-risk rows
- 📑 Export as PDF and archive locally

---

## 📁 Repository Contents

| File            | Description                             |
|------------------|-----------------------------------------|
| `AI Privacy Analyzer.json`  | Main n8n workflow definition             |
| `README.md`      | This file — detailed setup documentation |

---

## 💬 Support & Contributing

We welcome ideas and contributions!  
Feel free to:

- Open an issue
- Submit a pull request (PR) to improve the prompt, actions, or output
- Suggest privacy enhancements or risk scoring models

---

## 🧾 License

This project is MIT Licensed.

Use responsibly. No warranties provided.
Please follow data privacy laws in your jurisdiction (e.g., GDPR, HIPAA).

---

## 👤 Author

Created by Yogesh Ramesh  
🔗 GitHub: [https://github.com/Yoge-ra](https://github.com/Yoge-ra)

---


