The Sakila Project Codebase Analyzer is a comprehensive AI-driven pipeline designed to automatically analyze Java source code from a GitHub repository and extract meaningful insights. Specifically, this tool clones the SakilaProject, parses and processes its Java files, generates semantic embeddings for each code segment, and performs intelligent querying and summarization using advanced language models.

This project is built for software engineers, technical analysts, educators, and documentation teams who want to gain a deep and quick understanding of an unfamiliar or large-scale Java codebase. Rather than manually reviewing thousands of lines of code, users can rely on this automated solution to summarize the purpose of code blocks, list out functions and their roles, and assess overall code complexity with reasoned scoring.

At its core, the system combines Natural Language Processing (NLP) and semantic search through the following key components:

    ✅ Repository Cloning: Automatically fetches the Sakila Java project from GitHub using GitPython.

    📄 Code Parsing: Recursively reads all .java files and combines their content into one master string.

    ✂️ Chunking: Breaks the full codebase into manageable chunks (~800 characters) to allow for focused analysis.

    📈 Embeddings Generation: Uses HuggingFace's sentence-transformers/all-MiniLM-L6-v2 model to convert each chunk into a high-dimensional semantic vector.

    ⚡ FAISS Indexing: Builds a high-performance FAISS index for fast semantic search over the embedded chunks.

    🔍 Semantic Querying: Users can input a natural-language question (e.g., "How is a new user added to the database?") to retrieve the most relevant code snippets.

    🤖 Gemini LLM Integration: Each code chunk is passed to Google's Gemini 1.5 model with a structured prompt to extract:

        A high-level overview of what the code does

        A list of important functions with their signatures and brief descriptions

        A complexity score (out of 10) with an explanation

    📊 Result Aggregation: All Gemini responses are combined to form a single structured analysis document summarizing the entire project.

    💾 Output: The final results are stored as a JSON file (sakila_final_analysis2.json) which includes a consolidated overview, function summaries, and complexity assessment.

This project demonstrates the powerful synergy of open-source machine learning tools (HuggingFace, FAISS), vector databases, and LLMs (Gemini) in performing automated code analysis, documentation, and comprehension.
