---
title: "The New RAG Method that Sees the Page Instead of Reading It"
video_id: "90kPA7DOdRk"
youtube_url: "https://www.youtube.com/watch?v=90kPA7DOdRk"
publish_date: "2026-06-18"
duration: "13:54"
duration_seconds: 834
view_count: 2198
author: "The AI Automators"
description: |
  👉 Access our Starter Apps & AI Architects course in our community
  https://www.theaiautomators.com/?utm_source=youtube&utm_medium=video&utm_campaign=tutorial&utm_content=pixel-rag
  
  🔗PixelRAG 
  Demo: https://pixelrag.ai/
  GitHub Rep: https://github.com/StarTrail-org/PixelRAG
  Research Paper: https://github.com/StarTrail-org/PixelRAG/blob/main/assets/pixelrag-paper.pdf
  
  🔗Other Resources
  ColPali (arXiv): https://arxiv.org/abs/2407.01449
  VisRAG (arXiv): https://arxiv.org/abs/2410.10594
  DeepSeek-OCR (arXiv): https://arxiv.org/abs/2510.18234
  
  When an AI agent comes back empty handed, it's usually not because the answer wasn't there. It's because it didn't survive being flattened into text. Almost every agent grounds itself in some body of content, and the first step is nearly always the same: convert a messy page or PDF into markdown, where tables, charts and diagrams don't always survive the trip. 
  
  New research from Berkeley, Princeton, EPFL and Databricks puts a number on it: over a third of failures on a 1,000-question Wikipedia benchmark traced back to parser loss.
  
  So they asked a more radical question. What if you don't convert the page to text at all? That's PixelRAG. Render each page as an image, tile it, embed the tiles with a vision model, and hand the screenshots straight to a VLM at query time. 
  
  In this video I walk through the architecture, demo the app indexing over 7 million Wikipedia pages, and show the PixelShot skill in Claude Code reading a diagram WebFetch couldn't touch, along with the practical caveats before you'd adopt any of it.
  
  ⏱️ Timestamps:
  
  00:00 Demo
  05:11 PixelShot Agent Skill
  06:56 Architecture
  09:33 Findings and Conclusions
  
  #AI #AIAgents #RAG #PixelRAG #VisionRAG #VLM #ColPali #VisRAG #DeepSeekOCR #Docling #ClaudeCode #WebFetch #AgenticRAG #ContextEngineering #AIArchitects #AIBuilder

yt_tags:
  []



# AI-enriched metadata
content_type: "Framework"
primary_topic: "AI Agents"
difficulty: "Intermediate"
audience:
  - "Engineers"
  - "Executives"
  - "Product Managers"
entities:
  companies:
    - "GitHub"
    - "Databricks"
  people:
    []
  products:
    - "Claude"
    - "Claude Code"
    - "Make"
    - "Opus"
  models:
    - "DeepSeek"
concepts:
  []
summary:
  - "# The New RAG Method that Sees the Page Instead of Reading It

When an AI agent goes looking for information, it can often come back empty-handed"
keywords:
  - "ai-agents"
  - "ai-news"
  - "ai-tools"
  - "anthropic"
  - "claude"
  - "claude-code"
  - "coding"
  - "databricks"
  - "frameworks"
  - "github"
  - "leadership"
  - "make"
  - "meta"
  - "opus"
  - "tutorials"
  - "workflows"
---

# The New RAG Method that Sees the Page Instead of Reading It

When an AI agent goes looking for information, it can often come back empty-handed. Usually not because the answer wasn't there. It may be sitting right in the source. In a lot of cases, the problem is it didn't survive being turned into something the model could actually read. This is just as true for a coding agent interrogating documentation on the web as it is for a knowledge agent searching across a stack of reports. Almost every useful agent has to ground itself in some body of content and that content first has to be translated into something the model can actually read. And that translation step is where things can quietly fall apart. And the reason is that real sources are messy. A web page, a PDF, a Word document, they're full of complex layouts tables charts diagrams footers, and all of that has to be flattened down into a format an LLM can consume. The universal format for that is markdown. Everyone is converging on that. And that's okay for simple text and standard formatting, headers, bullets, etc. But it gets quite lossy the moment the source gets complicated. A table, a chart, the visual hierarchy of a page, they don't always survive the trip. And if you look at Claude Code's web fetch tool, it converts web pages to text. And for PDFs, there is also automatic text extraction, but it's missing diagrams and charts and images. People are working hard on solving this problem. We've covered DocLens a good few times on this channel and they've gone as far as building their own format, which is DocTags, specifically to capture complex documents more faithfully than plain markdown can. It's these types of advanced parsers that enable some pretty neat functionality when building custom AI systems. This is a citation preview and verifier that I went through in my last video. I'll leave a link for this in the card above if you'd like to see it. But there's only so far any of these parsing techniques can take you because, however clever the format, you're still translating the page into text, and some things always get left behind. Which brings me to research released over the last couple of weeks from a team at Berkeley, Princeton, and Databricks, who put a number behind how much just gets left behind in this translation process. And on the simple QA benchmark that they tested, which encompasses 1,000 factual Wikipedia questions, they analyzed all of the failed tests, and over a third of cases were down to this parser loss, where the HTML to text conversion destroys content before ever being searched. So, they asked a more radical question, which is, what if you don't convert the page to text at all? And it is a genuinely interesting idea. The old way here, for a knowledge base, let's say, is to take a page, parse it to extract the text, embed that text into a vector database for vector or hybrid search, and then an agent will search the database. Whereas, the new way would be a screenshot would be taken of that page, and then you would have a visual embedding created, and that would be indexed in your knowledge base, available for search. And within this pipeline of a vision embedding model and a vision language model, there is no text anywhere. So, that lossy step is gone. And while this makes sense for the likes of knowledge bases, it also applies for a live agentic searches, similar to the web search and web fetch example I showed with Claude earlier. Because both knowledge base search and live search both rely on parsing of text. The team who wrote the paper have open-sourced an application that shows this in action. So, this is available on GitHub. I'll leave a link for this in the description below. Here's a quick demo of this pixel rag technique in action, where it's interrogating over 7 million Wikipedia pages that were indexed. So, firstly, you can test out the vision embedding model. So, if you were to search for, let's say, The Starry Night, then this returns back all of the tiles, all of the screenshots that have a high similarity score to The Starry Night. And what influences that relevancy is the strength of the embedding model and how it has been trained. So, it's obviously able to pick up the text, but then also the imagery that's on these tiles. Now, a lot of these are quite visual, but you can see here that there is a tile returned that doesn't have any images. But, you can see the word Starry Night is mentioned there. So, this is a totally visual search engine. There's no text within any of these results, nor do these screenshots have any metadata in terms of keywords that can be searched. If you go to the agent mode, here we are doing the same thing. We're using the visual embedding model to search, but then we're passing those screenshots to an AI agent, a vision language model, to be able to answer a question. So, how many shots on target did Inter Milan have in the 2010 Champions League final? It carries out the search, and then it's returning screenshots. And as you can see, it's then studying the screenshots to formulate the answer. And it's a text-based answer because the LLM was able to analyze the images. They've actually made this Pixel RAG application available as an agent skill that you can use within Claude Code. So, Claude Code typically uses web fetch, which converts the HTML to markdown. Whereas, within this Pixel RAG repo, they've made this Pixel Shots skill. It only takes three commands to actually install it. And that provides you a slash command that you can use to then trigger Claude Code to take a screenshot of the source webpage. And because Opus 4.8 is a multimodal LLM, it's able to actually read that screenshot. One of the examples in the research report is this formations diagram on a Wikipedia page. When I asked Claude Code to use web fetch to see what formations the team had on this page, and I provided the Wikipedia page, it triggered the web fetch tool, but it said that I can't actually see the formations and it explains it converts the page to markdown. Actually, I used a different match here. This was Bayern versus Inter. So, yeah, the web fetch wasn't able to figure out this formation because it's essentially a diagram, whereas this pixel shot skill was able to take a screenshot of the page and it was able to confirm that Inter's shape is 4-2-1-3, so 4-2-1-3, and Bayern's shape reads as 4-2-2-2. So, you see that in lines there. And of course, that makes sense cuz it's essentially a screenshot. Now, it's worth noting that this is a much longer process than just carrying out a simple web fetch. And I also had to set some paths as environment variables for these plugins to work, so it could access the likes of Chrome to trigger Playwright. And because it does take a lot longer than standard web fetch, I would recommend only using it if web fetch is failing for a particular use case that you have. And what's interesting about this is it's almost like OCR in reverse because the old way of OCR was to turn a picture of a document into text. And that's because for decades machines were essentially blind. They couldn't read a page as a page. And web parsing comes from the very same instinct. You flatten the rich HTML, the visual page down to plain text because text was all the model could actually take. Whereas vision language models have come on leaps and bounds over the last 12 months and they read a rendered page the same way you do. So, they can see the layout, the tables, bold text, all intact. So, Pixel Rag, it kind of runs OCR backwards. Instead of turning a picture into text for the blind machine, it renders the page into a picture and hands that picture to the model so that it can see it. And that's the whole idea. Don't parse the page. Don't convert it to text at all. Just screenshot it. So, the architecture then is you render every page as an image at a fixed width, and then step two is you slice it into fixed height tiles. From the research report, here's an example of a full web page that they screenshotted, whereas here we have example tiles that were returned as part of the retrieval pipeline in response to a search. And it's the same here, if you type in The Starry Night and search, you'll see the different tiles that are retrieved. So, once the potentially really long page is split into these fixed height tiles, those screenshots are then sent into a vision embedding model, which is similar to a text embedding model. It produces an embedding, which is essentially a vector in high-dimensional space, and it inserts that into a vector database. And what's important here is that this vector represents the image, it's not encoding the text. So, then at query time, these tiles are returned to a vision language model who has the ability to then read the image. So, nowhere within this pipeline is there actually any text, which is a really interesting architecture. And it might sound like this wouldn't necessarily help for plain text questions where it is just text embedded on a screenshot, but they benchmarked the VLM reading the images versus OCRing the images when they were returned. And the VLM was slightly better at answering the questions because it is dodging that parser loss that we talked about earlier. And they did this at scale. They indexed 7 million Wikipedia pages, 30 million screenshots or tiles, the whole encyclopedia stored as pictures. And what's interesting about the findings in this report is that the AI agent was not the cause of over 90% of the failures. So, the answer was either destroyed by the parser in that parser loss example, or it's buried by the ranker. So, it actually does exist in the knowledge base, but it just falls outside of the top K that was retrieved. Now, when reviewing papers like this, I tend to take the stats with a grain of salt because most of them beat a baseline that in reality actually runs in production. So, of course, the new thing usually wins. But, in essence, I'm far more interested in the architecture because that's where the ideas live that could be reused and repurposed. And that's essentially the point of this video. And the paper also claims a bit of an efficiency win as well. So, they put this Pixel RAG library behind a multi-hop research agent and compared it how many tokens it burned against traditional text RAG. And on text retrieval, the agent ran through 37 and 1/2 million prompt tokens, whereas Pixel RAG only ran through 3.6 million, about a tenth. This does actually make sense because each tile, each screenshot, it packs a lot more information than a text chunk. The agent then ran through fewer searches and carried less history. So, less turns means less token consumption. So, while there is a saving, let's say at inference time, the actual ingestion is a lot more costly. They ran eight H100s for two full days across these 7 million Wikipedia pages. So, as you can see, this is an interesting RAG architecture or just a tool to fetch live data from the web. But, if you are weighing up whether to go the text parsing route versus using vision embedding and language models, there are a few things to consider. The first is that there is a hard floor on the LLM that you use. So, below a certain size and class of vision model, pixels seriously lose a lot of accuracy. According to the report, they lose by more than 12 and 1/2 points in their benchmarks. So, small models, they can't reliably read text that's been rendered as an image. And according to their research, the crossover sits around the 4 billion parameter VLM mark, which should be good enough to run on consumer hardware. And in my example earlier, I was using Opus 4.8, which is over a trillion parameters. So, all frontier AI models are highly capable at reading images like this. But, if you are deploying locally, you need to stay above the 4 billion parameter mark. Even though the paper talks about how there is an efficiency win using this approach, if anything, the cost is just moving. From a rag perspective, there is still an ingestion pipeline. Before you'd be using something like DocLing to actually parse documents, and then you're using a text embedding model and saving that to a database. With this approach, you are taking screenshots, you're splitting those screenshots into tiles, and you still are using an embedding model. The difference now, though, is you have all of these screenshots that you actually need to store. In their example of 7 million Wikipedia pages, these raw tiles, around 30 million of them, took up over 5 terabytes of space. And you're also running a vision model on every query now, instead of just cheap text. Now, we did see with DeepSeek OCR's research a few months ago that if you have very dense tiles, they can actually be cheaper to read in pixel by pixel than having lots of text to read in. So, it's not fully clear-cut which is going to be cheaper from an inference perspective. The idea of using a vision embedding model to feed a vision language model isn't exactly new. There's the Colli Palli paper from 2024. There's also this VizRag paper. But, I think the difference with this pixel rag approach is actually just the scale of it. Scaling across 7 million Wikipedia pages. I'll leave links to both of these in the description below if you'd like to read further. I wouldn't necessarily be dumping my rag pipelines for this pixel-based approach. But, in reality, modern agentic rag is all about hybrid retrieval. And that's either a case of routing particular documents to different types of mechanisms, like having a visual index versus a text index, or alternatively providing an AI agent with multiple retrieval tools, and it can choose the best one for the job. If you'd like to learn more about advanced agentic retrieval, then definitely check out our AI Architects course. We have a module dedicated to it that has 17 individual lessons that covers hybrid retrieval in serious depth. Everything from knowledge graphs, vector search, hybrid search, knowledge base exploration, document exploration, uh compiled knowledge, I cover it all there. And on that topic, if you would like to see how a compiled knowledge layer can improve your agent's accuracy, then check out this video here. Thanks for watching and I'll see you in the next one.
