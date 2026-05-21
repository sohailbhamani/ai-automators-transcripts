---
title: "Claude, GPT-5, Gemini 3: Only 1 of 52 Jobs They Can Actually Do"
video_id: "6X2g4alL250"
youtube_url: "https://www.youtube.com/watch?v=6X2g4alL250"
publish_date: ""
duration: "unknown"
duration_seconds: 0
view_count: 0
author: "The AI Automators"
description: ""

yt_tags:
  []



# AI-enriched metadata
content_type: "Framework"
primary_topic: "AI Tools"
difficulty: "Intermediate"
audience:
  - "Product Managers"
entities:
  companies:
    - "Microsoft"
    - "GitHub"
  people:
    []
  products:
    - "GPT-5"
    - "Claude"
    - "Gemini"
    - "Opus"
  models:
    - "GPT-5"
    - "Claude 4"
    - "Gemini"
    - "Gemini 3"
concepts:
  []
summary:
  - "# Claude, GPT-5, Gemini 3: Only 1 of 52 Jobs They Can Actually Do

Last month, Microsoft researchers published a paper that proves that even the best LLMs consistently corrupt documents when you deleg"
keywords:
  - "ai-news"
  - "ai-tools"
  - "anthropic"
  - "career"
  - "claude"
  - "frameworks"
  - "gemini"
  - "github"
  - "google"
  - "gpt-5"
  - "microsoft"
  - "openai"
  - "opus"
  - "product-management"
  - "workflows"
---

# Claude, GPT-5, Gemini 3: Only 1 of 52 Jobs They Can Actually Do

Last month, Microsoft researchers published a paper that proves that even the best LLMs consistently corrupt documents when you delegate editing tasks to them. This is fascinating because at the same time, Microsoft is currently selling this delegation of tasks as a commercial offering in their co-pilot product suite. And this delegate 52 benchmark that they published is used for simulating and evaluating LLMs on long horizon delegated workflows where LLMs edit professional documents on behalf of knowledge workers. Everything from robotics accountancy aviation translation, slides, the works. Each of these 310 environments consists of real documents and 5 to 10 complex editing tasks that a user might ask an LLM to carry out. So these are not singleshot delegation tasks and the results of these tests are pretty staggering. They evaluated 19 LLMs from six different families. This large-scale experiment revealed that current models degrade documents during delegation. And even Frontier models like Gemini 3.1 Pro, Claude 4.6 Opus, GBT 5.4, Four, they corrupt an average of 25% of document content by the end of long workflows with an average degradation across all models of 50%. And the way these errors show up matters as well. When the researchers examined individual runs, they found models maintain nearperfect reconstruction of the documents in most rounds. However, they then experience catastrophic single round failures that lose 10, 20, even 30 points in a single turn. Frontier models tend to corrupt content in documents while preserving the structure, which makes their failures a lot harder to actually detect. Whereas weaker models tend to delete content entirely, which is much more obvious to actually spot. Degradation depends on the domain as well. So, LLMs perform better in programmatic domains like Python or databases and worse in natural language and niche domains like earning statements or music notation. The paper is currently under peer review. However, they have released the benchmarks as a GitHub repo, so you can actually test this out yourself. And that's exactly what I
