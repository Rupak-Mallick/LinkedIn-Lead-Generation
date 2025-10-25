# 🚀 LinkedIn Lead Generator (AI-Powered via n8n + Groq + Google Sheets)

An automated **LinkedIn Lead Generator** workflow built using **n8n**, **Groq LLM**, and **Google Sheets** — designed to help you extract and organize targeted LinkedIn leads effortlessly.  

---

## 🧠 Overview

This workflow takes a simple text input like:  
> “investment banking directors in Atlanta”  

and automatically:  
1. Extracts **Job Title**, **Industry**, and **Location** using an **LLM Chain** (Groq).  
2. Performs a **Google Custom Search** (filtered to LinkedIn profiles).  
3. Extracts clean profile data (Name, Title, Snippet, and LinkedIn URL).  
4. Appends all results directly to a **Google Sheet** for easy access and tracking.  

---

## ⚙️ Tech Stack

- **n8n** – Workflow automation platform  
- **Groq LLM (llama-3.3-70b)** – Natural language understanding & text extraction  
- **Google Custom Search API** – To fetch relevant LinkedIn profiles  
- **Google Sheets API** – For storing extracted lead data  

---

## 🧩 Workflow Structure

| Node | Description |
|------|--------------|
| **Chat Trigger** | Starts the flow when a message/input is received |
| **Basic LLM Chain** | Extracts job title, industry, and location from user input |
| **Structured Output Parser** | Ensures structured JSON output from the LLM |
| **HTTP Request** | Uses Google Custom Search API to find LinkedIn profiles |
| **Code (JavaScript)** | Parses search results and extracts clean lead data |
| **Google Sheets** | Appends the leads (Name, Title, Snippet, URL) into your Sheet |

---

## 🧰 Setup Instructions

### 1️⃣ Prerequisites
- [n8n](https://n8n.io) installed or cloud account created  
- A **Groq API Key** (for LLM operations)  
- A **Google Custom Search API Key** + **Search Engine ID (CX)**  
- A **Google Sheet** connected via OAuth in n8n  

### 2️⃣ Import the Workflow
1. Download the file: `LinkedIn lead generator.json`  
2. Import it into your n8n dashboard.  
3. Connect your credentials for:
   - **Groq API**
   - **Google Sheets**
   - **Google Custom Search**

### 3️⃣ Configure Keys
In the **HTTP Request** node:
```bash
key = YOUR_GOOGLE_API_KEY
cx = YOUR_CUSTOM_SEARCH_ENGINE_ID
```

### 4️⃣ Connect Google Sheet
Make sure your Google Sheet contains columns:
```
Name | Title | Snippet | Url
```
Paste your Sheet URL in the **Google Sheets node**.

---

## 💼 Example Use Case

Input:  
```
marketing managers in Dubai
```

Output in Google Sheet:  

| Name | Title | Snippet | URL |
|------|--------|----------|-----|
| Sarah Ahmed | Marketing Manager at XYZ Agency | Experienced in digital marketing... | linkedin.com/in/sarah-ahmed |
| John Doe | Marketing Manager at ABC Group | Focused on brand strategy... | linkedin.com/in/john-doe |

---

## 💡 Potential Applications

- 🔹 Lead generation for **sales teams & agencies**  
- 🔹 Candidate sourcing for **recruiters**  
- 🔹 Competitive or market research  
- 🔹 Enriching CRM databases automatically  

---

## 🧱 Future Improvements

- Integrate **LinkedIn API (if available)** for direct data access  
- Add **email enrichment tools** (e.g., Hunter.io)  
- Build a simple **frontend interface** to trigger workflows  

---

## 📜 License

This project is open-source and free to use for educational or personal automation purposes.
