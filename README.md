# ⚡ Ultra-Fast AI News Sentiment Pipeline (Groq & Llama 3.3)

![Project Screenshot](screenshot.png)

## 🚀 Overview
This project demonstrates a high-performance automated **ETL (Extract, Transform, Load)** pipeline designed to analyze global technology news in real-time.

Built with **n8n** running on **Docker**, this agent leverages the **Groq API** to utilize the **Llama 3.3 70b** model for lightning-fast sentiment analysis. It fetches raw RSS data, processes it with near-instant latency, and exports structured business intelligence reports.

## 🛠️ Tech Stack
* **Orchestration:** [n8n](https://n8n.io/) (Self-hosted via Docker)
* **AI Engine:** Groq API (Llama 3.3 70b Versatile)
* **Performance:** Low-latency inference via LPUs (Language Processing Units)
* **Data Source:** RSS Feeds (Dynamic Ingestion)
* **Containerization:** Docker Desktop
* **Output:** Structured .XLSX Reports

## ⚙️ How It Works (The Workflow)
1.  **Ingestion:** The system monitors specific RSS feeds for new content every minute.
2.  **Optimization:** Uses batch processing to handle data streams efficiently.
3.  **AI Analysis:** Sends article titles to **Groq Cloud**. The **Llama 3.3 70b** model evaluates the context and classifies the sentiment as `POSITIVE`, `NEGATIVE`, or `NEUTRAL` in milliseconds.
4.  **Data Structuring:** Merges the raw title with the AI-generated insight.
5.  **Storage:** Automatically generates and saves an Excel report locally.

## 📦 Installation & Usage

### Prerequisites
* Docker installed on your machine.
* A [Groq Cloud](https://console.groq.com/) API Key.

### Steps to Run
1.  Pull the n8n Docker image:
    ```bash
    docker run -d --restart unless-stopped --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n n8nio/n8n
    ```
2.  Open `http://localhost:5678` in your browser.
3.  Import the `workflow.json` file provided in this repository.
4.  Add your **Groq API Key** in the credentials section (using HTTP Request or Groq Node).
5.  Execute the workflow!

## 📈 Future Improvements
* Real-time dashboard visualization using Grafana.
* Slack/Discord alerts for high-impact negative news.

---
*Created by [Furkan Bitik / https://www.linkedin.com/in/furkanbitik/]*
