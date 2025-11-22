🤖 Hybrid Python FAQ Chatbot (Retrieval + Gemini AI)

A smart chatbot that answers Python-related questions using a Hybrid Intelligence System:

🔍 Retrieval-Based Answers using TF-IDF + Cosine Similarity

💡 Generative AI Fallback using Gemini 2.5 Flash

🎨 Beautiful CLI Interface with colors

🧠 Domain-restricted expert Python assistant

This ensures every user query receives a correct, high-quality response.

🌟 Features
🔹 1. Retrieval-Based Question Answering

Uses TF-IDF vectorization

Computes cosine similarity

Returns the most relevant FAQ answer

Threshold-based confidence (≥ 0.75)

🔹 2. Generative AI Fallback

If no close FAQ match is found:

Query is automatically sent to Gemini 2.5 Flash

System prompt restricts it to Python-only answers

Prevents hallucination & off-topic responses

🔹 3. Beautiful Console Chat UI

Colorized prompts (yellow, blue, green, magenta)

ASCII-styled chatbot headers

Distinguishes retrieval & AI answers visually

🔹 4. Full NLP Preprocessing

Using nltk:

Tokenization

Lowercasing

Lemmatization

Stopword removal

Punctuation cleanup

🛠️ Tech Stack
Component	Library / Algorithm	Purpose
Vectorization	TfidfVectorizer	Transform questions into numeric vectors
Similarity	Cosine Similarity	Retrieve closest FAQ match
NLP Cleaning	nltk	Prepare data for accurate matching
Generative AI	Gemini 2.5 Flash	AI fallback for unseen queries
Console UI	colorama	Colored user experience
📌 Project Workflow
User Question
      ↓
Preprocessing (nltk)
      ↓
TF-IDF Vectorize
      ↓
Cosine Similarity ≥ 0.75?
      ↙                     ↘
Yes (FAQ Match)       No (Fallback to Gemini)
Return Answer          Generate Python-specific answer

📚 Example Chat Outputs

✔ Retrieval example:

User: How to install software on Windows?
Bot: Similar question found!
FAQ Match: "How to install Python?"
Answer: Download Python from python.org...
Similarity: 77.8%


✔ Fallback example:

User: What is a decorator in Python?
Bot: This question is not in my FAQs, using generative AI…
Bot: A decorator is a function that modifies another function...


✔ Domain restriction:

User: What is the capital of France?
Bot: I only answer Python-related questions.

▶️ Running the Chatbot
1. Install dependencies
pip install nltk scikit-learn google-generativeai colorama

2. Add your Gemini API key
genai.configure(api_key="YOUR_API_KEY")

3. Run the chatbot
python chatbot.py

🏆 What This Project Demonstrates

Real chatbot engineering

NLP preprocessing

Retrieval vs Generative AI

API integration

Hybrid intelligence systems

Console UI design

Exception handling

Production-quality code structure

Perfect for:

University submission

AI/Machine Learning assignments

Software engineering portfolio

GitHub showcase
