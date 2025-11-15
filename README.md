# SEO ChatBot – Intelligent SEO Analysis Agent

## Overview

The **SEO ChatBot** is an intelligent, agentic, AI-powered SEO assistant built using **LangChain**, **Groq Llama 3.3**, **SerpAPI**, **DataForSEO**, **BeautifulSoup**, and **Gradio**.  
It performs **Technical SEO**, **Content Quality Analysis (via RAG)**, **URL extraction**, **Rank Tracking**, **Meta Tag extraction**, **Comparison of websites**, and **Keyword generation**—all integrated inside an automated tool-driven agent architecture.

This project is designed to simplify and automate SEO analysis by letting the user interact using natural language—just provide a website URL or keyword, and the chatbot performs a full analysis using multiple SEO modules.

![SEO Chatbot Flow](./Seo-chatbot-flow.png)

---

## Key Features

###  **1. URL Extraction & Validation**
- Extracts URLs from user text using an LLM.
- Validates URLs (404 checks, redirects, dead links).

###  **2. Technical SEO Module**
- SSL/HTTPS check  
- PageSpeed Insights (Desktop & Mobile)  
- Mobile Friendliness  
- Broken Link Scanner  
- Sitemap & Robots.txt Analysis  
- Backlink Count (DataForSEO)  
- URL Structure Quality  

###  **3. Content Analysis Module (RAG-based)**
- Loads Google Search Quality Evaluator Guidelines PDF.
- Uses embeddings + vector database.
- Performs LLM-based content scoring:
  - Overall Rating  
  - Strengths  
  - Weaknesses  
  - Summary  

###  **4. URL Rank Module**
- Uses SerpAPI to retrieve search engine organic results.
- Finds rank for the given keyword.
- Retrieves top 5 competitor websites.

###  **5. URL Comparison Module**
- Compares two websites across:
  - Technical SEO  
  - Meta Tags  
  - Content Quality  
  - Rank  

###  **6. Keyword Generator Module**
- Extracts search phrases from user message.
- Provides SEO-optimized keyword suggestions.

###  **7. Agentic ChatBot**
- Built using LangChain Tools + ReAct Agent.
- Chooses tools based on user intent.
- Uses memory to maintain context.
- Streams responses via Gradio UI.

---

##  Project Structure

```
.
├── app.py                       # Main Gradio + Agent Execution App
├── Seo-chatbot-flow.png         # System Architecture Diagram
├── README.md                    # Documentation
├── requirements.txt             # Dependencies
├── .env                         # API Keys (SERP API, DataForSEO, GROQ)
└── ...
```

---

##  Tech Stack

### 🔹 **AI / LLM**
- Groq Llama 3.3 (via ChatGroq)
- LangChain ReAct Agent
- RAG using VectorStore + FastEmbed

### 🔹 **SEO APIs**
- SerpAPI
- DataForSEO

### 🔹 **Python Libraries**
- BeautifulSoup  
- Requests  
- PyPDFLoader  
- InMemoryVectorStore  
- Gradio  

---

##  Installation & Setup

### **1. Clone Repo**
```bash
git clone https://github.com/your-repo/seo-chatbot.git
cd seo-chatbot
```

### **2. Install Dependencies**
```bash
pip install -r requirements.txt
```

### **3. Setup Environment Variables**
Create `.env` file:

```
SERP_API_KEY=your_key
DATAFORSEO_LOGIN=your_login
DATAFORSEO_PASSWORD=your_pass
GROQ_API_KEY=your_groq_key
```

### **4. Run the Chatbot**
```bash
python app.py
```

### **5. Access the UI**
Open:
```
http://127.0.0.1:7860
```

---

## Usage Examples

### 🔸 Rank my website for specific keyword  
> "Check my website www.example.com for the keyword *best dentist in Mumbai*"

### 🔸 Full Technical SEO Audit  
> "Audit https://example.com for technical SEO issues"

### 🔸 Compare two sites  
> "Compare example1.com vs example2.com in SEO"

### 🔸 Content Quality Check  
> "Evaluate the content quality of https://example.com/blog/article"

---