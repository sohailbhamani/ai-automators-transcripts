---
title: "The Problem With Vision Language Models"
video_id: "rLmAmxuxPjQ"
youtube_url: "https://www.youtube.com/watch?v=rLmAmxuxPjQ"
publish_date: "2026-01-22"
duration: "1:10"
duration_seconds: 70
view_count: 3873
author: "The AI Automators"

yt_tags:
  []



# AI-enriched metadata
content_type: "Tutorial"
primary_topic: "AI Strategy"
difficulty: "Intermediate"
audience:
  - "General"
entities:
  companies:
    - "Mistral"
  people:
    []
  products:
    - "Gemini"
  models:
    - "Gemini"
    - "Mistral"
concepts:
  []
summary:
  - "# The Problem With Vision Language Models

If you're using vision language models for document extraction, there's something you need to know"
keywords:
  - "ai-agents"
  - "ai-tools"
  - "career"
  - "frameworks"
  - "gemini"
  - "google"
  - "mistral"
---

# The Problem With Vision Language Models

If you're using vision language models for document extraction, there's something you need to know. While VLMs like Gemini, GPT5, and Mistral are incredibly powerful, they are by their very nature generative. They're not extracting text. They're predicting text based on what they see. And while this can work very well for messy scans or handwriting, it can lead to hallucinations. And for a lot of use cases, that's fine. But if you need verbatim scans, verbatim data extraction, then the predictive nature of these VLMs is probably just not good enough. And this is where tools like Dockling come in. Dockling standard pipeline has a series of non-generative AI models that are purpose-built for text extraction, recognizing headers, table layouts, and all while preserving the semantic structure of the document. And this standard pipeline isn't necessarily smarter than the VLM. It's just a different tool for the job. You can also run VLMs through Dockling as well. Dockling is completely open source and runs locally, which is why it's our go-to for building fully grounded AI agents. Check out the link below if you'd like to watch how I build and deploy a fully local AI rag agent.
