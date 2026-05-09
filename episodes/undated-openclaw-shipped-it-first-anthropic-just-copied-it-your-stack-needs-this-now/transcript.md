---
title: "OpenClaw Shipped It First. Anthropic Just Copied It. Your Stack Needs This Now."
video_id: "mmBddcUFltU"
youtube_url: "https://www.youtube.com/watch?v=mmBddcUFltU"
publish_date: ""
duration: "unknown"
duration_seconds: 0
view_count: 0
author: "The AI Automators"
description: ""

yt_tags:
  []


# AI-enriched metadata
content_type: "Tutorial"
primary_topic: "AI Agents"
difficulty: "Beginner"
audience:
  - "Engineers"
  - "Executives"
entities:
  companies:
    - "Anthropic"
    - "GitHub"
    - "Box"
  people:
    []
  products:
    - "Claude"
    - "Make"
  models:
    []
concepts:
  - "How do you build this feature into your own agentic system? and when should you actually use it? at a high level, dreaming is a scheduled background process that runs between your active sessions"
summary:
  - "Antropic just announced a new feature in their managed agents called dreaming to help their agents self-improve over time"
keywords:
  - "ai-agents"
  - "ai-news"
  - "ai-strategy"
  - "ai-tools"
  - "anthropic"
  - "box"
  - "career"
  - "claude"
  - "coding"
  - "frameworks"
  - "github"
  - "leadership"
  - "make"
  - "product-management"
  - "workflows"
---

# OpenClaw Shipped It First. Anthropic Just Copied It. Your Stack Needs This Now.

Antropic just announced a new feature in their managed agents called dreaming to help their agents self-improve over time. And last month, OpenClaw released a similar feature with the same name. So, what exactly is going on behind the scenes here? And importantly, how do you build this feature into your own agentic system? And when should you actually use it? At a high level, dreaming is a scheduled background process that runs between your active sessions. These can review your agent sessions and memory stores, extract patterns and curate memories so your agents improve over time. There was a good article published last year on Leta's website. Let is a memory first coding agent and they have been a bit ahead of the curve with some of these concepts. As they state here, agents experience prolonged periods of sleep time. If these agents are stateful, then sleep time is an opportunity to apply compute. We have a simple example here where sleeptime computer is used to consolidate and curate memories. So within the original context of the agent, there might have been entries related to a particular topic and perhaps even conflicting ones. And scheduled jobs can be used to create clean, concise, and detailed memories, cutting out duplication, ordering information, and trying to make sense of what's important and what's not. Antropica applying the same general concept here. Let Claude reflect on past sessions to curate an agent's memory and surface new insights. Claude writes to memory stores as your interaction with agents on their manage agent platform. But naturally over many sessions, a memory store accumulates duplicates, contradictions, and stale entries. And that's what this dreams feature is intended to solve. And this dream process will read an existing memory store alongside past session transcripts, then produce a new reorganized memory store. So it doesn't actually modify the original one. Rather, it creates a separate one. So you can discard that if you like. But Dreaming is a research preview feature with pretty limited details on implementation. And it's part of Claude's managed agents, which can certainly have its downsides, namely cost, vendor lockin, and not necessarily as much control as you might want. And Daniel went through the landscape of managed platforms in a recent video on our channel. Also, by using generalized memory systems, you run the risk of running into many different memory antiatterns. One of the worst ones being memory poisoning, where injected instructions survive across sessions and might execute days or weeks later. If you want to build the best memory system for your agent, it's generally best to be deliberate about its design. In fact, we have a lesson dedicated to this specifically within our AI architects course. One of the biggest downsides of using managed agent platforms is that generally the memory will get locked into that platform specifically, which can make it difficult to switch to other providers. But the good news is that you can absolutely build this type of memory layer into your own agentic system. So the question is how would you do that? For a more concrete example of how dreaming works, how this memory consolidation layer works, we jump to openclaw because they make the process extremely transparent. If you clone the openclaw repo, if you go to the memory core folder, you can see all of the files related to this dreaming feature. And you can point your coding agent be it cloud code or codeex at these files and get it to analyze the implementation and then build a similar memory system into your own AI system. So let's have a look at how openclaw stores memories overall because there are some useful insights in here. Openclaw remembers things by writing plain markdown files in your agents workspace. The model only remembers what gets saved to disk. And by the way, you can still analyze and pick from this architecture and then write and retrieve from a different form of storage such as vector databases or SQL databases or graph databases, especially if markdown files don't work particularly well for your use case. But markdown can actually scale surprisingly well. Within OpenCloud, there are three memory related files. We have the memory MD. This is long-term memory, durable facts, preferences, and decisions. And these are loaded at the start of every DM session. Then we have daily notes markdown files and this is running context and observations. Today and yesterday's notes are loaded automatically. And then we have the dreams markdown file which is what we're interested in here. When dreaming is enabled on an openclaw instance, it stores two kinds of files. The machine state is stored within this folder. And then we have human readable output in this dreams markdown file. And as the dreams process is running, it may promote specific items to the memory. MD file which is loaded at the start of every DM session. When OpenClaw goes through a dreaming sweep, it runs them in phases. So it goes between light, and deep. So it really leans pretty heavily into this dream idea. Within the light phase, it sorts and stages recent short-term material. Within it reflects on themes and recurring ideas. And then finally, at the deep stage, it scores and promotes the durable candidates and then writes those to the memory MD file if necessary. and those most important memories will get loaded into the context of every session with OpenClaw. This deep phase may update the memory markdown file as well as add information to the dreams.m MD file. Deep ranking signals are used to determine what's actually worth saving. So for example, we have frequency, how many short-term signals the entry accumulated and relevance, average retrieval quantity for the entry. And as thism phase of the sleep cycle is run, it records reinforcement signals used by this deep ranking feature. Before we go any further, let's take a step back and determine where does this actual dreaming memory consolidation feature fit into your process and where it does not. One good example is where your agent has the same shape of work over and over again. So legal drafting or support ticket triage or where your agent is making the same mistakes and missing the same context over and over again. That reputation is really good raw material as a consolidation pass in a memory dream feature. Also, when your agent spends the first 20 minutes of every run rediscovering what it needs to do or what conventions to follow and if skills have not been created for those particular tasks. And if you want that information to be picked up slowly and continuously by the agent, then again, this is a good use case. And you can also have pretty sophisticated versions of these memory consolidation systems working across multiple users, which can be very useful, but also bring in its own challenges. This kind of feature doesn't fit so well if you have widely varied work and if you have oneoff or short-lived agents and also if you need to know exactly what your agent knows without having to go through the process of examining all of the memory consolidation which can sometimes take up more time than it saves then it might not fit the process. Also memory can bloat and contradict itself and bake in the wrong lessons and that can be one of the many failure modes that I showed earlier. Memory is a very deep concept in AI engineering and it takes so many different shapes and so many different forms and the landscape is huge. Markdown files in a file system can go a lot further than most people realize. But there are a lot of other options. You can store data in a standard relational database or you can use external platforms and services like M0 which uses hybrid vector and a graph memory layer. Or you can use services like Zep. We've included Zep in some previous systems that we demonstrated on this channel and that uses this graffiti library under the hood which you can also use separately. When you look at Hermes, a popular open claw alternative, this has its own persistence memory layer out of the box which you can also dig into within their GitHub repo. This system can also easily integrate out of the box with external memory providers such as Honcho or M0 that I talked about a minute ago. There's a steady move in the AI industry to build systems so that agents can actually improve over time. And what Antropic have shipped here essentially seems to be a managed harness wrapper around a pattern that the open source ecosystem has been settling on for quite a while. And these patterns are being pushed in order to try to overcome all of the familiar problems that we're used to dealing with, such as when you have to say the same thing to agents over and over again and when they forget important information over time. But there's still quite a long way to go and memory systems in general can introduce more problems than they intend to solve. If a bad memory gets baked in, the agent can be confidently wrong over the long term and stale information can get treated as current. Memory consolidation can be extremely useful and it does not need to be isolated just to markdown files, but it's only part of the answer and a generalized dream layer very rarely beats one that's designed for a specific agent for your specific domain. And if you want to go deep into learning how to build expert level specialized AI systems, then make sure to check out the link in the description below to the AI Architects course in our community. We currently have over 15 hours of footage and new lessons are getting added regularly. Thanks for watching.
