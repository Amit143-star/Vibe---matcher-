# Vibe---matcher-
Vibe Matcher — Fashion Recommendation Prototype

A lightweight, embedding-based vibe matching system built with OpenAI & cosine similarity.

Overview

Vibe Matcher is a mini recommendation engine that takes a text vibe query (e.g., “energetic urban chic”) and finds fashion products that best match the vibe using:

✅ OpenAI text embeddings
✅ Cosine similarity
✅ Simple ranking logic
✅ Evaluation + latency measurements

This prototype demonstrates how AI can power modern product discovery by focusing on vibes, style intent, and semantic meaning — not just keywords.

 Features

✅ 1. Product Dataset

5–10 mock fashion products

Each product includes name, description, and vibe tags


✅ 2. Embedding Generation

Uses text-embedding-ada-002

Automatically falls back to synthetic embeddings if no OpenAI API key is found

Allows easy offline testing


✅ 3. Vector Search

Embeds product descriptions

Embeds user vibe query

Computes cosine similarity using sklearn

Returns Top-3 recommendations with scores


✅ 4. Evaluation

Marks similarity > 0.7 as “good match”

Runs 3 example queries

Includes latency plot using timeit


✅ 5. Reflection

Lists production improvements

Suggests multi-modal image embeddings, vector DB, user-feedback tuning, etc.

 Architecture

User Query 
      ↓
OpenAI Embedding (or fallback)
      ↓
Cosine Similarity Search
      ↓
Rank Results → Top 3
      ↓
Evaluation + Thresholding



 Project Structure

vibe_matcher_repo/
│── vibe_matcher_notebook.ipynb   # Full prototype implementation
│── README.md                     # Project documentation
│── requirements.txt              # Libraries needed


---

Running the Notebook

Option 1 — Google Colab

Just open the notebook in Colab and run all cells.

To use real embeddings, set your key:

import os
os.environ["OPENAI_API_KEY"] = "sk-..."

Option 2 — Local Jupyter Notebook

Install dependencies:

pip install -r requirements.txt

Run:

jupyter notebook
 Example Query

Input:
"energetic urban chic"

Output:
Top-3 recommended products sorted by cosine similarity
(with score + fallback message if below threshold)


 Future Improvements

Switch to a vector database (Pinecone, Milvus, Weaviate)

Add image embeddings for multi-modal retrieval

Introduce user feedback loop for better ranking

Train a small style classifier for faster pre-filtering

Add spell-checking, query expansion, and trend-aware tuning


 Why This Matters

Fashion shoppers often search using moods, vibes, events, or feelings rather than product names.
This system transforms natural-language intent into actionable product recommendations, showcasing how AI can enhance discovery in any modern shopping experience
