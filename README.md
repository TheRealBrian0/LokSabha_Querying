# LokSabha_Querying
**NLP Query System for Lok Sabha Policy Discussions**
I'm excited to share my latest project — an NLP-powered document search and summarization tool designed specifically to help users query Indian Lok Sabha discussions and get targeted answers about policies that impact their daily lives.

🔎 **Purpose & Use Case:**
A farmer can ask, "_What policies are discussed about vegetable price regulation_?"
A gold merchant can query, "_Are there any new policies that might affect gold prices_?"
Citizens can get summarized insights about tax policies, agriculture bills, or economic reforms directly from Parliament discussions!
This project aims to make large-scale government transcripts accessible to ordinary people in a simplified way via search + summarization 💪

🧠 **Model Used:**
The project uses the lightweight MiniLM (all-MiniLM-L6-v2) model from Hugging Face.
✅ Pre-trained & publicly available at HuggingFace.
✅ Ideal for real-time search because it balances speed and accuracy.
✅ Lightweight models like MiniLM ensure that even users with modest hardware can run these tools without high GPU/TPU requirements — making it truly accessible.

🛠️ **Step-by-Step Technical Process**
PDF Reading:
Reads multiple Lok Sabha PDFs containing speeches and policy discussions using pdfplumber.
Text Embedding:
Uses sentence-transformers to convert documents into dense vector embeddings.
MiniLM generates a numerical representation that captures meaning and context.
FAISS Index Creation:
Facebook AI Similarity Search (FAISS) is used to index these embeddings.
This allows for efficient nearest-neighbor search across hundreds or thousands of documents.
L2 Similarity Search:
When a user asks a question, the system converts their query into an embedding.
Uses L2 distance (Euclidean distance) to find documents most similar to the query via FAISS.
L2 search ensures relevant results based on vector proximity.
Focused Summarization:
Uses NLTK to tokenize and score sentences, selecting the most query-relevant lines.
Summarizes results, so users see direct, concise answers instead of full documents.
User-Friendly GUI:
Built with Tkinter for easy usage.
Users can select folders, enter queries, and view results — no coding needed!
Accessible even for those unfamiliar with technical tools.

🔮 **Future Scope:**
Plan to extend it for state-level assemblies.
Support queries in regional Indian languages.
Add voice query option to further improve accessibility.
