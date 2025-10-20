# 🌟 Anime Insight: Hybrid-AI Summary Generation

[![Live Frontend](https://img.shields.io/badge/Live%20Application-GitHub%20Pages-blue)](https://priyam2324.github.io/Anime_Insight/)
[![Backend Deployed on](https://img.shields.io/badge/Backend%20Logic-Hugging%20Face%20Spaces-yellow)](https://huggingface.co/spaces/Priyam2307/Anime_Insight_BE)
[![Made with](https://img.shields.io/badge/Made%20with-Gemini%20API%20%26%20spaCy-informational)](https://ai.google.dev/gemini-api)

**Anime Insight** is a specialized web application that generates **nuanced, balanced, and spoiler-free thematic summaries** of anime and manga. It achieves this by combining official community scores with localized theme extraction and advanced Large Language Model (LLM) synthesis, providing high-quality analysis that reflects community consensus.

---

## 🌐 Try the Live Application

The application is deployed and fully operational. Follow these simple steps to generate a summary:

1.  **Access the App:**
    Navigate to the live frontend link: **[https://priyam2324.github.io/Anime\_Insight/](https://priyam2324.github.io/Anime_Insight/)**

2.  **Enter the Title:**
    In the search bar, type the name of the anime or manga you want summarized (e.g., "Demon Slayer" or "My Hero Academia").

3.  **Select & Wait:**
    * The frontend initiates the connection to the backend (proactively solving the "cold start" problem).
    * Select the correct media entry from the results.
    * Wait a few moments while the system fetches data, performs local theme extraction, and synthesizes the final summary using the Gemini LLM.

4.  **Receive the Insight:**
    The balanced, spoiler-free summary reflecting the community's official score will be displayed on the page.

---

## 💡 Technical Overview: Optimized Workflow

The core functionality utilizes a **Decoupled Hybrid-AI Architecture** designed for speed and consistency, strategically distributing tasks across local and cloud resources.

### 1. The Core Analysis Pipeline

| Stage | Component | Primary Role & Optimization |
| :--- | :--- | :--- |
| **A. Data Retrieval** | Python Backend (Flask, Requests) | Uses **Smart Search Logic** to find the media and retrieves the **Official MAL Rating**. **Local sentiment scoring is bypassed** for consistency. |
| **B. Local Theme Extraction** | Python Backend (**spaCy**) | Scrapes spoiler-free reviews and uses local NLP to extract the **Top 7 frequently discussed Noun Chunk Themes** and supportive sentences. |
| **C. LLM Synthesis** | **Gemini API** (Cloud AI) | Receives the Official Score and the thematic evidence. It uses this package to generate a professional summary that **reflects the score's tone** (e.g., highly positive for a high score) without mentioning the numerical value. |

### 2. Deployment and Architecture

| Component | Technology Stack | Deployment Platform | Key Robustness Feature |
| :--- | :--- | :--- | :--- |
| **Frontend** | HTML, CSS, JavaScript | **GitHub Pages** | **Proactive Server Pinging** to manage cold start and prevent user crash errors. |
| **Backend** | Python, Flask, spaCy | **Hugging Face Spaces** | **Secure Credential Handling** (`os.getenv()`) for all API keys, preventing public exposure. |

---

## ⚠️ Note on Backend Deployment

The Backend is hosted on a Hugging Face Space configured to run a **Flask API endpoint**, not a traditional visual application.

* **Space URL:** `https://huggingface.co/spaces/Priyam2307/Anime_Insight_BE`
* **Error Reason:** If you visit the Space URL directly, it displays a "Not Found" error. **This is intentional** because the deployment uses a Gradio environment strictly for its fast **API hosting capabilities** and does not host a visible Gradio front-end app.
* **To View Logic:** To inspect the core Python logic (Flask routing, spaCy theme extraction, and Gemini synthesis), please navigate to the **Files** section of the Hugging Face Space.
