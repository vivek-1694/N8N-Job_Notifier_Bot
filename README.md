# Automated Job Opportunity Tracker (n8n)

An end-to-end workflow automation that ingests job-related emails, parses details using a privacy-first LLM parser, enriches company information via HTTP requests, logs everything to Google Sheets, and enables real-time interactive actions via Telegram (connected through webhook + ngrok).

---

## 🚀 Workflow Overview

Here’s how the automation works step by step:

1. **📩 Gmail Trigger** → Whenever Gmail receives a job-related email, the workflow is triggered automatically.  

2. **🤖 LLM + Parser** → Extracts key details (Job ID, Company Name, Role, Sender, Subject). *(No sensitive personal data is ever sent to LLMs.)*  

3. **🌐 HTTP Request** → Fetches the company’s official website and a short description for quick context.  

4. **📊 Google Sheets** → Logs all details — including user actions — so I can revisit every opportunity and track past decisions.  

5. **📲 Telegram Bot** → Instantly sends a structured message with job details and asks:  
   - Do you want to know more about the company?  
   - Should I generate a tailored resume?  
   - Or simply skip this one?  

6. **👂 Real-time replies (Webhook + ngrok)** →  
   - The Telegram bot is connected to n8n using a **webhook**, so it continuously listens for my replies.  
   - Since n8n is running locally, **ngrok** is used to expose the webhook endpoint to the internet, ensuring instant and seamless communication between Telegram ↔ n8n.  

---


## ▶️ Demo

🎥 A working demo is available in docs/demo.mp4, showing how the workflow runs end-to-end for a sample email.