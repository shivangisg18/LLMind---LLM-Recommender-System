# LLMind---LLM-Recommender-System
Choosing the right LLM is increasingly difficult as different models excel at different tasks.

This project builds an end-to-end, data-driven LLM recommender by analyzing sentiment from 2,440 real user posts, it learns which LLMs perform best for specific tasks and recommends models like ChatGPT, Claude, or Gemini using a semantic, data-driven pipeline.

## Pipeline & Methodology

The system is built as a modular NLP pipeline that transforms raw Reddit discussions into a task-specific LLM recommendation engine. Each stage is implemented in a dedicated Jupyter Notebook for clarity and reproducibility.

### 1) [Topic Modeling](Topic%20Modeling.ipynb)

Analyzes ~2,440 Reddit posts from major LLM communities

Uses BERTopic to identify 10 core user use cases, covering both practical tasks (e.g., coding, image generation) and common pain points

### 2) [Sentiment Analysis](Sentiment%20Analysis.ipynb)

Applies a RoBERTa-based transformer tailored for social media text

Classifies posts as positive, negative, or neutral

Captures nuanced user feedback beyond rule-based sentiment methods

### 3) [LLM Identification](NER.ipynb)

Determines which LLM is discussed in each post

Combines explicit mention detection with subreddit-based inference

Maps all mentions to standardized parent LLM brands

### 4) [Knowledge Base](Knowledge%20Base.ipynb)

Merges use-case labels, sentiment, and LLM identity

Aggregates sentiment at the LLM × use-case level

Computes a Positive Experience Score to quantify model performance for each task

### 5) [Recommendation Engine](LLM%20Recommender.ipynb)

Accepts natural-language user queries

Uses semantic similarity (Sentence-BERT) to identify the relevant use case

Ranks and recommends LLMs based on real user satisfaction
