# ClipCompanion
Rag Based Application

Developed an AI powered Retrieval Augmented Generation (RAG) system enabling users to query YouTube video content in natural language without watching the video.

Implemented automatic transcript extraction from YouTube videos using the YouTube Transcript API, handling exceptions for videos with disabled captions or unavailable transcripts.

Processed video transcripts by splitting them into smaller, manageable chunks using RecursiveCharacterTextSplitter to improve semantic understanding and retrieval efficiency.

Generated vector embeddings for each transcript chunk using sentence-transformers/all-MiniLM-L6-v2 via HuggingFace embeddings, and stored them in a FAISS vector database for fast and accurate semantic retrieval.

Built a retrieval pipeline leveraging FAISS to perform similarity-based searches over transcript embeddings, allowing the system to retrieve the most relevant contextual segments in response to user queries.

Designed a prompt template for the Google Gemini LLM, ensuring answers are contextually grounded in the retrieved transcript segments and instructing the model to respond only with information available in the video.

Integrated the LLM into a RAG workflow using LangChain runnables and parallel chains, combining retrieved context with user questions to generate precise, context-aware responses.

Enabled efficient handling of multiple queries by structuring the retrieval and generation pipeline to reuse embeddings and document chunks, optimizing performance for large video transcripts.
