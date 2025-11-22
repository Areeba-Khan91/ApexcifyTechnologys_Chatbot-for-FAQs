Hybrid Python FAQ Chatbot (Retrieval + Generative AI)
✔ Objective

To develop a hybrid chatbot system capable of answering Python-related questions using:

Local FAQ Retrieval (TF-IDF + Cosine Similarity)

Generative AI Fallback using Gemini 2.5 Flash

This ensures that every possible question receives an answer, either from pre-written FAQs or via generative AI.

1. Data Preparation & Preprocessing
FAQ Dataset

A curated set of domain-specific Python FAQs was prepared, covering installation, pip usage, GIL, tuples vs lists, and ML libraries.

NLP Cleaning (nltk)

Each question was preprocessed using:

tokenization

lowercasing

stop-word removal

lemmatization

punctuation cleanup

This created a normalized dataset for accurate similarity matching.

2. Retrieval System (TF-IDF + Cosine Similarity)
Vectorization

Each cleaned FAQ question was converted into numerical TF-IDF vectors using TfidfVectorizer.

Matching Algorithm

When a user asks a question:

The query is preprocessed the same way.

A similarity score is computed with cosine similarity.

The highest-matching FAQ is identified.

Similarity Thresholding

A high threshold (0.75) ensures that retrieval activates only for very close matches, preventing incorrect FAQ suggestions.

3. Hybrid Logic (Generative AI Fallback)
If Match Found (≥ 0.75)

→ Return precise FAQ answer

If Match Not Found (< 0.75)

→ Forward query to Gemini 2.5 Flash with a strict system instruction:

“You are an expert Python programming assistant. Only answer Python-related questions.”

This prevents off-topic hallucinations and keeps output domain-specific.

Error Handling

Handled API errors, missing keys, and exceptions gracefully.

4. User Interface (CLI)

A professional, color-coded interface was created using colorama.

Features include:

Color-coded distinction of Retrieval answers and AI answers

Pretty ASCII-styled chatbot boxes

User prompt styling

Display of similarity score for transparency

5. Demonstration Output (Working Proof)

The log clearly demonstrates:

Gemini Response for Novel Questions

✔ “What is a decorator?” → Gemini
✔ “What is Python?” → Gemini
✔ “Difference between Python 2 and 3?” → Gemini
✔ “factorial function?” → Gemini

Retrieval Match

✔ “How to install software on Windows?”
Matched with FAQ: How to install Python? → 77.8% similarity

Domain Restriction Working

✔ “What is the capital of France?” →
Bot refuses and enforces Python-only rule.

Exit Condition

✔ “quit” → graceful shutdown

Everything in your logs shows perfect hybrid operation.
