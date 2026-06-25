---
title: "Sakana and OpenRouter Say They Beat Fable 5. With Everyone Else's Models."
video_id: "30SS92PD3fU"
youtube_url: "https://www.youtube.com/watch?v=30SS92PD3fU"
publish_date: "2026-06-24"
duration: "10:35"
duration_seconds: 635
view_count: 697
author: "The AI Automators"
description: |
  👉 Access our Starter Apps & AI Architects course in our community
  https://www.theaiautomators.com/?utm_source=youtube&utm_medium=video&utm_campaign=tutorial&utm_content=fugu
  
  🔗 Sakana Fugu
  Announcement: https://sakana.ai/fugu/
  Trinity (arXiv): https://arxiv.org/pdf/2512.04695
  Conductor (arXiv): https://arxiv.org/pdf/2512.04388
  
  🔗 OpenRouter Fusion
  Announcement: https://openrouter.ai/blog/announcements/fusion-beats-frontier/
  Fusion: https://openrouter.ai/fusion
  
  A research lab most builders have never heard of just claimed it beats Fable 5. The twist is that Sakana Fugu isn't a model at all. You hit one endpoint, and behind it a trained orchestrator picks from a pool of frontier models, delegates the work, verifies it, and stitches the answer back together. It can even call copies of itself.
  
  A week earlier, OpenRouter shipped Fusion: the same bet in a different shape. Stop leaning on one model. Send the prompt to a panel and let a judge merge the answers. Two labs, one idea.
  
  So this video answers the question underneath both launches: is a mixture of specialist models actually better than one general-purpose model? 
  
  #AI #AIAgents #SakanaAI #Fugu #OpenRouter #Fusion #MixtureOfModels #ModelRouting #MixtureOfAgents #LLMRouting #AIArchitecture #AIArchitects #AIBuilder #Claude #Opus #AgentArchitecture

yt_tags:
  []



# AI-enriched metadata
content_type: "Framework"
primary_topic: "AI Strategy"
difficulty: "Advanced"
audience:
  - "Engineers"
  - "Executives"
  - "Product Managers"
entities:
  companies:
    - "OpenAI"
    - "Anthropic"
    - "Box"
    - "Together AI"
  people:
    []
  products:
    - "Gemini"
    - "Opus"
  models:
    - "Gemini"
concepts:
  []
summary:
  - "Yesterday, Sakana AI, a research lab out of Japan, released Fugu and Fugu Ultra"
keywords:
  - "ai-agents"
  - "ai-news"
  - "anthropic"
  - "box"
  - "career"
  - "coding"
  - "frameworks"
  - "gemini"
  - "google"
  - "openai"
  - "opus"
  - "prompting"
  - "together-ai"
---

# Sakana and OpenRouter Say They Beat Fable 5. With Everyone Else's Models.

Yesterday, Sakana AI, a research lab out of Japan, released Fugu and Fugu Ultra. And their claim is big, which is frontier-level performance up against Anthropic's Fable 5 without the export control risk that resulted in Fable 5 and Mythos being taken offline. The interesting thing about Fugu is that it's not your traditional model. Sakana calls it a multi-agent system that's delivered as a single model. You hit one API and behind it Fugu uses a specialist orchestrator to pick from a pool of frontier models, Opus, GPT, Gemini. It delegates pieces of a task, checks the work, and stitches the answer back together. And it can even call copies of itself. As you can see, this is very different to your typical AI model. Sakana has released two tiers. There's plain Fugu, which is the everyday one, and Fugu Ultra is the expensive, hard task one that throws a team at the problem. Sakana claims to beat Fable 5 and has produced a number of benchmarks where Fugu Ultra is above Fable 5, the likes of Terminal Bench 2.1, the Live Code Bench. I honestly hold very little stock in benchmarks like these. These are vendor produced and unverified. The community reaction to the Fugu models since its release is split. The general average view I'm picking up is that you'd likely get slightly better results just running any one of the underlying models like GPT 5.5 or Opus 4.8 on their own without the added cost and complexity of the likes of Sakana. But I'm not really here for the benchmarks as I'm much more interested in the architecture behind Fugu and is it something you should be replicating yourself when building your own AI systems because this is not your typical monolithic model. It's an orchestration model and one that Sakana claims is going to be the next frontier in AI architecture. And the pitch here is that you get better results by leaning on each model's strengths and dodging its weaknesses. And that's the real question. Is a mixture of specialist models actually better than a single general purpose frontier model? And this idea is absolutely not new. Two weeks ago Open Router, they shipped Fusion, which is the same idea in a different shape. So, you don't lean on a single model, you combine several models. And at a high-level, there are three broad approaches you can take here. The first is to go solo, which is what most people do. So, it's one provider at a time, one prompt, one model, and one response. Now, obviously, with that single call, there may be sub-agents that are spun up to break a task apart, but essentially, you are getting a single response back from the call. And this is effectively what Sakana is comparing itself against when it produces its benchmarks. The second is routing. So, within this pattern, something is looking at the task and picks the best model for the job. And this is the Sakana Fugu design. You can kind of think of this as a mixture of models approach, where you're orchestrating between whole models. Obviously, different to mixture of experts, which is within a single model. And the third is fusing. So, here you're asking several models at once, and then a judge merges the answers together. And that's what I just showed you with Open Router Fusion. And the cost shape to Fugu is already different to Fusion here, because with Fusion, you're taking multiple answers plus a judge every time. So, it gets quite expensive, particularly when you take into account that you're paying API fees, and you're not exactly getting this on a subscription plan. And these types of patterns are not new. They're exactly the same as what we teach in our Harness Architectures lesson in our AI Architects course. The difference here is that when you're designing and building your system, you choose the models, you design the logic, you pick the validation criteria. Whereas with Sakana and Open Router, all of that is abstracted away. So, it's just a single model API call, and all of this routing or fusion logic happens on the server-side. And if we zoom in on the Fugu solution, it is essentially a black box. Behind the endpoint, it selects, delegates, verifies, and synthesizes. So, a simple request may only need one worker. A hard one may convene an entire team. This is what they call real trained orchestration and not just a wrapper prompt. And it's worth focusing on that because this trained orchestration is actually a model in itself. So, Sakana aren't actually incorrect when they call Fugu a model, but really their model is an orchestration model that sits in front of the frontier models. And the problem here is that this isn't an open-source orchestration model. It's completely closed and hosted. There are no weights available. The routing is essentially hidden by design. So, when you get an answer back, you have no idea which model actually produced the answer or why it was chosen. So, in essence, you're trusting a black box to spend your money wisely on models you can't actually see it pick. And this type of model routing has been a category for quite a while. Not Diamond is a great example, which is an intelligent model router for coding agents. The difference here is they don't claim to be a model, let's say. They're not benchmarking themselves against the underlying models in the stack. So, most of this is essentially air traffic control routing. You look at the prompt, you pick a model, and you send the request there. Fugu is probably closer to the shape of this router or one application. And within this pattern, you have a system that thinks, it routes, it reads the result, and it routes again, maybe to a different model. So, there's a lot more planning involved in this type of orchestration. Now, it's quite possible that Not Diamond are doing something similar here as well. Because the secret sauce to this type of architecture is in the orchestrator. And Sakana conducted two pieces of research leading up to this release. The first research system under Fugu is Trinity and it's a tiny frozen model that is 600 million parameters plus a control head with under 20,000 learnable parameters. And within each turn, it picks one of seven models within a pool and it gives it a role. So it's either tinker, worker or verifier and it stops when the verifier accepts the work. The second piece of research was on a conductor. So this is a 7 billion parameter model trained with reinforcement learning to write the workflow as text. The subtasks, which model handles each one and who gets to see who's output. Fusion is the opposite move. So here it's fanning out and sending your prompt to a panel of models all in parallel. They produce their responses and then a judge model will read those answers and they'll synthesize a merged final response. And when doing that, it's told to find consensus, contradictions, gaps and blind spots. So in this case, you're picking the panel and the judge and all of that is then merged into the final response. And this is essentially the LLM council pattern which you may have seen. LLM blender, mixture of agents, the LLM council that Andre Karpathy produced. It's effectively the same idea except it's actually productized and packaged with a single API endpoint. And it's funny because open router already have routing using smart auto mode. Fusion is then almost moving up the ladder from route to a single model to fuse a panel of models. There has been some decent research on this fusion idea. So with the mixture of agents research conducted by Together AI, you throw several different models at a prompt and let an aggregator merge their answers. And the diversity here is supposed to be the secret sauce. However, there was a Princeton paper that actually found the opposite. If you take your single best model and sample it several times and merge the responses from that, you beat the mixed panel. And the reason is that there's a quality versus diversity trade-off. So reaching for variety drags weaker models into the room and that drop in quality hurts more than the variety actually helps. If you compare these two architectures together, you should be getting better results from a routing architecture because you should be picking the best possible model for the job. With fusion, however, you are going to be aggregating the results from lots of different models and the weaker ones, as I described, will drag down the quality of the merged answer. But you can never outperform the best model that's in the pool for a specific task. However, across all benchmarks, if you were playing to the strengths of all of the different models, the overall baseline should in theory be slightly higher. But then there's a question at what cost? Because model providers obviously want to lock you into their environments. That's why they have subscription plans. And these plans are great because you can control the cost and if you take advantage of the various 5-hour windows, you can absolutely maximize your token usage. Whereas with the likes of Open Router, you're paying for every single token because it's a raw API meter. Another point to note on Sakana's press release is they talk about the geopolitical risks on being locked into a specific vendor. And they talk about Anthropic's fable and the various export that were placed. And by orchestrating the world's models, we are delivering the realistic resilient blueprint required for AI sovereignty. And that's all well and good, but essentially by choosing Sakana, you are just shifting your vendor lock-in from the likes of Anthropic to now Sakana because this is a black box. It's a closed orchestrator on closed models. Before you didn't control the model, whereas with Sakana, you don't control the orchestrator that orchestrates the models. So, if Anthropic or OpenAI shut down access to their models, the quality of the likes of Sakana would clearly drop. So, I think the point here is, if you genuinely wanted a router or a fusion-style architecture, you should build it yourself. Be in total control over the logic, the routing, the model selection, and that's definitely the case with you're building AI products like we do in our community. This is the starter app we have, which is a full-stack AI agent platform. And because this is a Python and React app, you have total control over what models you choose, and the logic around which ones are called for which task. Check out the link in the description if you'd like to learn more about our AI Architect's course or the starter apps within our community. If you're interested in AI architectures like what we discussed today, then check out this video here where I go through the generator-verifier pattern when building agentic rag applications. Thanks so much for watching, and I'll see you in the next one.
