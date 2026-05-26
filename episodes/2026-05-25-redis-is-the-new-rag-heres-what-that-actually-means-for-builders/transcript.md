---
title: "Redis Is The New RAG. Here's What That Actually Means For Builders."
video_id: "F-Ewm7qOr_c"
youtube_url: "https://www.youtube.com/watch?v=F-Ewm7qOr_c"
publish_date: "2026-05-25"
duration: "11:35"
duration_seconds: 695
view_count: 2587
author: "The AI Automators"
description: |
  👉 Access our AI Architects course & join hundreds of serious AI builders in our community: https://www.theaiautomators.com/?utm_source=youtube&utm_medium=video&utm_campaign=tutorial&utm_content=redis-iris
  
  🔗 Related videos and resources:
  Pinecone Nexus video: https://www.youtube.com/watch?v=0TPq43Wpbz0
  Self-service agent video: https://www.youtube.com/watch?v=OFZmezsx9bA
  Redis Iris: https://redis.io/iris/
  
  Redis has just announced Iris, a new architecture for AI agent retrieval that takes a very different approach to the knowledge layer problem. Rather than pre-compiling answers into a static artifact, Iris focuses on keeping a fast, navigable copy of your operational data that agents can query in real time, making it well-suited to environments where the underlying data changes frequently.
  
  In this video, I walk through the Redis Iris stack, what each component does, and how its runtime approach compares to build-time alternatives like Pinecone Nexus. We also compare against why naive RAG and even many agentic RAG configurations struggle in real production systems, especially in use cases like customer support where an agent needs to pull from databases, ticketing tools, shipping providers, and policy docs to answer a single question.
  
  What's covered:
  - Redis' four core requirements for agent retrieval at scale: navigability, speed, freshness, and self-improvement
  - Redis Data Integration (RDI) and how change data capture keeps an operational copy of your data in sync from sources like Postgres, Oracle, Snowflake, and MongoDB
  - Why mirroring data into Redis protects your transactional systems from being hammered by agentic workloads
  - Redis Context Retriever: defining entities, fields, relationships, and tools (find, get, search, filter) exposed via MCP or CLI with row-level access control
  - Redis Agent Memory: short-term session memory with custom TTL, plus long-term memory for preferences, learned patterns, and promoted session data
  - LangCache for semantic response caching, including similarity thresholds, search strategies, and the risks of stale or out-of-context cache hits
  - Redis Search across vector, structured, and unstructured data in a single index
  - Redis Flex, the new SSD-based storage tier for more cost-effective scaling beyond pure in-memory
  - A direct comparison of Redis Iris (runtime, fresh-on-demand) vs Pinecone Nexus (build-time, pre-compiled knowledge artifacts) and when each architecture fits best
  
  Chapters:
  0:00 - Overview
  2:12 - Requirements for agents at scale
  3:06 - What is Redis Iris
  4:25 - Redis Data Integration (RDI)
  5:37 - Redis Context Retriever
  6:28 - Redis Agent Memory
  7:18 - LangCache
  8:01 - Redis Search and Redis Flex
  8:50 - Not plug and play
  9:04 - Comparison vs Pinecone Nexus
  10:54 - No one-size-fits-all retrieval

yt_tags:
  []



# AI-enriched metadata
content_type: "Case Study"
primary_topic: "AI Strategy"
difficulty: "Advanced"
audience:
  - "Engineers"
  - "Executives"
  - "Product Managers"
entities:
  companies:
    - "Snowflake"
    - "MongoDB"
    - "Oracle"
  people:
    []
  products:
    - "Make"
    - "MCP"
    - "Artifacts"
    - "Projects"
  models:
    []
concepts:
  []
summary:
  - "There's a huge race in AI right now to define the next generation of rag"
keywords:
  - "ai-agents"
  - "ai-tools"
  - "artifacts"
  - "coding"
  - "frameworks"
  - "leadership"
  - "make"
  - "mcp"
  - "mongodb"
  - "oracle"
  - "product-management"
  - "projects"
  - "snowflake"
  - "tutorials"
---

# Redis Is The New RAG. Here's What That Actually Means For Builders.

There's a huge race in AI right now to define the next generation of rag. While you've probably heard claims that rag is dead way too many times by now, those are often overhyped and the solutions are generally too simplistic. Many players in the industry are converging on the idea of a knowledge or context layer between your agent and its underlying data sources as a much better alternative to conventional rag. But there's not a lot of agreement about what those solutions actually look like and they're generally not oneizefits-all. And now Reddus, one of the real pioneers in high-speed data retrieval, has just announced Iris with an architecture that's really worth taking seriously if you're building AI agents that rely on large scale fastch changing data spread across many different data sources because these are serious weaknesses of most AI retrieval systems. And by the way, we have no affiliation with Reddus whatsoever. We've in fact never done a sponsored video on this channel, but we can all take inspiration from Reddis's architecture here without even having to use their stack directly. Let's start with some context. Back a few months ago, the CEO of Reddus was quoted saying, "I've seen fewer examples of real successful production agents than I would have imagined in terms of anything outside of engineering." And to be fair, AI agents have often underdelled in production systems across the board. And there's a huge gap between a flashy demo and one that survives real world data and real use cases. He also wrote in this blog post, "The hardest problems in production AI are no longer solved by model choice. They show up at runtime. stale state, slow retrieval, fragmented memory, disconnected tools, and sessions that fail to compound. And the example he uses here is a customer support bot. A customer might ask, "Why is my order late?" Think about everything the agent needs to actually answer that question, especially in bigger organizations, such as the customer database, the order system, the shipping provider, the ticketing tool, and the policy docs. Naive rag is almost never going to work in these kind of use cases and it can still be quite a challenge for a lot of agentic rag configurations. We've covered similar solutions to this on our channel before such as giving your AI agent lock down access to a readonly view on your database and we go very deep into agentic retrieval strategies within our AI architects course linked in the description. But let's look through exactly what Reddus are offering here. Before we dig into it here, they have a good list here of requirements for agents to function at scale. Of course, everything mentioned here is a focus of their product offering, but it is still a good list to give some context up front. First off, the agent should be able to navigate throughout a large amount of data. It should be able to traverse relationships, understand entities, discover relevant context, and so on. Secondly, context should be retrievable quickly, which in most cases is a very true requirement. Aenta gra systems can often be very slow if they have quality retrieval strategies behind the hood and they may work through many loops to retrieve the correct information. Third, context that is always up to date. Agent retrieval pipelines are often too slow for anything near real time and the data your agent retrieved 10 minutes ago might already be stale and out of date. And the fourth is the self-improvement aspect that most AI agents don't really remember interactions, information, and context as they should. So, what exactly is Reddus Iris and how are they looking to solve those challenges and meet those requirements? First off, Iris is a stack of Reddit services and not all of them are new. Iris has just been announced at the time of recording this video. So, this is definitely not a hands-on tutorial or review of their service, but rather an explainer of the retrieval architecture they're using, which is quite different to many other AI context layer solutions in the industry. At a very high level, you have the data in the source systems, Oracle, Postrest, MongoDB, and you have this Reddus data integration that continually captures changes and syncs them into Reddus data structures. So now you've got an operational copy of the data within Reddus. Your agent can then interact with this data using the Reddus context retriever, which makes a CLI and MCP tools available to the agent. We'll talk about that in a minute. Reddus agent memory then tries to persist what it learns across sessions using a combination of both short-term and long-term memory. And then Reddus LAN cache caches responses and then tries to short circuit anything that's been answered before. So your agent never actually touches the operational data directly. It interacts with the data in the Reddus DB that's been synced via the Reddus data integration via MCP or CLI that's made available by the Reddus context retriever. So let's dig into those components because you probably have more questions than answers at this point. Let's start from the start with this Reddus data integration which is currently in public preview. RDI implements a change data capture pattern to sync data from a source database such as Postgress or Oracle, Snowflake or  and tracks that and updates the data into the Reddit data structures. This is how Iris is covering the requirements that we mentioned earlier of being always up to date. RDI mirrors a fresh copy of your data for the agent to hit at high speed and Reddus are the experts at lightning fast retrieval. So I wouldn't doubt them that much in that regard. And since they're making a copy of the data from the operational systems means that the agent is not going to bombard the transactional systems with requests because hitting operational data directly could be quite an issue for busy agentic systems where agents could be making thousands of times more requests than a human would. It also means that the data can be modeled in a manner that's more efficient from both a speed and indexing perspective and also in a more flattened denormalized structure that will make it a lot easier for your agents to interact with via tools. Of course, this idea of copying operational data to a different source is not exactly new. That approach is often used for analytics and caching for example. Next, the Reddus context retriever is the one that aims to deliver on the requirement for the agent to be able to navigate through your knowledge base. The idea here is that you define models of your business data, the entities, the fields and the relationships and these can then be executed via MCP or CLI via your agent. You can then define the data you want to give your agent access to along with role level access control. So your entities could be product or customer or order for example. And then you have tools. So these are the tools that your agent will then be able to call based on that data. For example, find product by range, get customer by ID, search customers by text, filter by tags, filter product in stock. So you have a bunch of different operations such as filtering finding getting searching. So it's giving the agent tools to more easily access your data as it needs without trying to get your agent to join data across lots of different tables or across different data sources, which can be incredibly unreliable in Aenta Gra. The Reddit agent memory includes both short-term and long-term memory features. For short-term memory, you can set a custom TTL which will be very important for systems where the source data might change very very frequently. And then they have long-term memory which stores extracted past sessions, user preferences, learned patterns, and other relevant data. And this is one of many memory solutions across the industry. For example, you have mem zero, honcho, dep graffiti. We have dreaming style features within cloud managed agents and openclaw, which I went through in a previous video, and much more. But for how the Reddus memory works, first off, we have the short-term memory, which is the session memory. And that's very important to maintain the current conversation state and session history. So the short-term memory will be stored temporarily. And certain elements, [clears throat] user preferences, patterns, and other relevant data may be promoted to the long-term memory, otherwise it's just deleted as per the TTL policy. Then you have the LANCA service. So instead of calling your LLM for every single request, you can use lang cache to check if a similar response has already been made previously and if so returns it instantly from the cache to save time and money. It sounds great. Semantic caching could be very useful for your projects, but it's also a potential minefield where you can get similar past responses that are actually out of context. When searching the cache, you can search by similarity thresholds and also search strategies either using exact search or semantic search. These can be pretty blunt instruments. So you really need to thoroughly evaluate systems that are using response caching like this. The data is queried within the system using Reddus search and that can search vector structured and unstructured data all within one index. Here you can see some Reddit search queries similar to SQL but with its own syntax. And there are lots of different types of queries from exact match, range, full text, geospatial, vector, combined and aggregation. Reddus also claim that you can easily scale to 1 billion vectors using their indexes which is pretty huge. And then they also have Reddis Flex which is a new SSDbased storage tier that they're offering. So you're not paying for every single thing to run in memory which could really make a difference in terms of pricing. So here Reddus are very much acknowledging that you cannot just magically solve retrieval with a very simple layer. It requires a modular stack. You need multiple services together and you need to be very cognizant of how you're using them. And it's very important to look past the marketing here. Retrieval here is certainly not just a solved problem by signing up for a Reddus account. This is not plug-and-play and it will require maintenance to make sure that the shape of your retrieval layer is up to date with the source operational data. And you need to model your source data along with relationships. Recently on our channel, Daniel covered Pine Cone Nexus, which is another knowledge layer approach to your AI agents, but it's quite a different architecture. Pine cone's new product offering here goes to build time. It pre-ompiles typed knowledge artifacts like related to sales, finance, support, and marketing. So the agent queries a pre-shaped answer instead of redriving it every single call. Whereas Reddus here goes to runtime. It doesn't try to premputee anything into a compiled knowledge layer. It makes the data structures fast and navigable. So the agent pulls fresh context on demand as it's quickly changing. And the two options here split pretty cleanly on where they're strong. Pine cones is more likely to be strong where you have a large stable knowledge base with recurring known questions, contracts, compliance manuals, and things like that where a pre-ompiled artifact is exactly right. When using Pine Cone's knowledge engine or anything like Andre Kapathy's wiki idea, anytime the source data changes, you need to recompile what's in the knowledge layer. Whereas Reddus' architecture here would be far more suitable to very fast changing data environments because in those cases a pre-ompiled artifact in a knowledge layer could be stale 5 minutes after it's created. When we're evaluating data retrieval solutions, we often have a use case in our mind from past experience or specific projects we've worked on. And there's certainly a segment of software professionals that are rolling their eyes when they see the Carpathy wiki idea or pine cone nexus idea of a compiled knowledge layer. They're likely to be thinking of use cases where the underlying data is changing very regularly. And even though this kind of architecture can be pretty complex, it may be what's required to make a reliable working AI agent in production. When you take a step back, there really is no onesizefits-all solution to retrieval. Conventional rag and simpler agent rag solutions were often touted as the magic solution, but in reality, flashy demos often don't translate to reliable production systems. Digging deep into retrieval strategies has been our main focus on this channel and community for quite a long time. And if you want to design a context and retrieval layer that will actually work in production, that's exactly what we cover in our agentic retrieval module inside the AR architects course in our community link in the description below. And I'd also highly recommend you check out our recent video covering Pine Cone Nexus, which Daniel went through on our channel, which uses quite a different architecture for their knowledge layer than the Reddus Iris architecture covered in this video. Thanks for watching.
