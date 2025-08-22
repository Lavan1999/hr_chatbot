# AI-Powered HR FAQ Chatbot  

An intelligent HR FAQ assistant built with **Flask**, **Sentence Transformers**, and optional **OpenAI LLM integration**.  
This chatbot allows employees to ask questions about HR policies and get instant, accurate answers grounded in a curated FAQ dataset.  

---

## 🚀 Features  

- **FAQ Retrieval** – Uses semantic search (Sentence Transformers) to find the most relevant answers.  
- **Fallback & Confidence Handling** – Provides direct answers or suggests multiple FAQs when uncertain.  
- **LLM Integration (Optional)** – If `OPENAI_API_KEY` is set, the chatbot leverages OpenAI models (default: `gpt-4o-mini`) for natural and friendly responses.  
- **Web UI** – A simple, responsive frontend built with HTML, CSS, and JavaScript.  
- **Reindexing** – Easily refresh embeddings when `faqs.csv` is updated.  

---

## 📂 Project Structure  



Project structure
├── app.py             # Flask app with in-memory embeddings
├── config.py          # Loads environment variables (API key, model, etc.)
├── faqs.csv           # HR FAQs (questions & answers)
├── faq_index.pkl      # Cached embeddings (used by app.py)
├── templates/
│   └── index.html     # Frontend interface
├── static/
│   └── style.css      # Styling for the chatbot UI
├── requirements.txt   # Python dependencies
└── README.md          # Project documentation

## ⚙️ Installation  

1. **Clone the repository**  

   git clone https://github.com/Lavan1999/hr_chatbot.git
   cd hr_chatbot
   python -m venv .venv

2. **Create a virtual environment & install dependencies**
source .venv/bin/activate   # on Windows: .venv\Scripts\activate
pip install -r requirements.txt

3. **Set environment variables (create a .env file)**
OPENAI_API_KEY=your_api_key_here   # optional
OPENAI_MODEL=gpt-4o-mini

🧠 How It Works

Embeddings – FAQ questions are converted into dense vectors using sentence-transformers/all-MiniLM-L6-v2.

Semantic Search – When a user asks a question, the chatbot retrieves the most relevant FAQs based on cosine similarity.

Answering –

If OpenAI API is configured, responses are synthesized in a natural, conversational way.

Otherwise, the system provides the most relevant FAQ answer(s).

📊 Example

User: "How many paid leaves do we get?"
Bot: "Employees are entitled to 12 paid leaves per year."

🔮 Future Improvements

Multi-turn conversations with context memory

Admin panel for uploading FAQs dynamically

Integration with Slack or MS Teams
