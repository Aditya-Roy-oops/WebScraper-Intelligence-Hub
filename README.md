# 🌐 WebScraper – Intelligent Website Chat Engine

WebScraper is a **Streamlit-based RAG (Retrieval-Augmented Generation) application** that transforms any public website into an **interactive AI-powered knowledge assistant**.
It crawls a website, indexes its content locally, and lets users ask **grounded questions strictly based on the website data**.

---

## 🚀 Features

* 🔗 **Website Crawling & Indexing**

  * Extracts clean textual content from any valid URL
  * Splits content into optimized chunks
  * Stores data in a persistent vector database (Chroma)

* 🧠 **AI-Powered RAG Chat**

  * Uses Google Gemini models for intelligent responses
  * History-aware questioning (context preserved)
  * Answers strictly from website content (no hallucinations)

* 🛡️ **Robust Fallback System**

  * If embedding or AI APIs fail:

    * Automatically switches to **keyword-based local search**
    * Ensures answers are still returned from raw website data

* 🧐 **Data Inspector**

  * View all extracted and indexed website text
  * Helps validate what the AI is actually using

* ⚡ **Model Selection**

  * Dynamically detects available Gemini models
  * Choose the best model for speed or quality

* 🧹 **Persistent & Resettable**

  * Vector database cached per URL
  * Reset app state anytime with one click

---

## 🗂️ Project Structure

```
WebScraper/
├── main.py             # Streamlit UI & core logic
├── requirements.txt    # Project dependencies
├── .env                # API keys (GOOGLE_API_KEY)
└── README.md           # Project documentation
```

---

## 🧰 Tech Stack

* **Frontend**: Streamlit
* **LLM**: Google Gemini (via `google-generativeai`)
* **RAG Framework**: LangChain
* **Vector DB**: ChromaDB (local persistence)
* **Web Scraping**: BeautifulSoup + LangChain Web Loader
* **Embeddings**: Gemini Embedding API with fallback safety
* **Environment Management**: python-dotenv

---

## 🔑 Prerequisites

* Python **3.9+**
* Google Generative AI API Key

---

## 📦 Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/Aditya-Roy-oops/WebScraper.git
   cd WebScraper
   ```

2. **Create virtual environment (recommended)**

   ```bash
   python -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

---

## 🔐 Environment Setup

Create a `.env` file in the root directory:

```env
GOOGLE_API_KEY=your_google_api_key_here
```

> ⚠️ Never commit your `.env` file to version control.

---

## ▶️ Running the Application

```bash
streamlit run main.py
```

The app will open automatically in your browser.

---

## 🧪 How It Works (Flow)

1. User enters a website URL
2. Website content is:

   * Crawled
   * Cleaned
   * Chunked
   * Embedded
   * Stored in a local vector database
3. User asks questions
4. System:

   * Retrieves relevant chunks
   * Generates answers using Gemini
   * Falls back to keyword search if AI fails
5. User gets **grounded, verifiable answers**

---

## 🛡️ Safety & Reliability

* ❌ No hallucinated answers
* 🔒 Answers strictly limited to indexed content
* ⚠️ Graceful handling of:

  * API quota limits
  * Timeouts
  * Embedding failures

---

## 📌 Example Use Cases

* Documentation Q&A bots
* Company website intelligence
* Research & content analysis
* Compliance or policy verification
* Learning assistants for blogs or tutorials

---

## 🧠 Future Enhancements

* Multi-page crawling
* Sitemap support
* File upload (PDF / DOCX)
* Export chat history
* Authentication & role-based access

---

## 📜 License

This project is released under the **MIT License**.
Feel free to use, modify, and distribute.

---

## 🤝 Author

Built with ❤️ for intelligent, grounded AI systems.
If you improve it — contribute back!
