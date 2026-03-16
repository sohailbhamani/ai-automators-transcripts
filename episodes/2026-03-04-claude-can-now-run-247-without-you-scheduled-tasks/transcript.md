---
title: "Claude Can Now Run 24/7 Without You (Scheduled Tasks)"
video_id: "A-xGGE3QQIM"
youtube_url: "https://www.youtube.com/watch?v=A-xGGE3QQIM"
publish_date: "2026-03-04"
duration: "8:43"
duration_seconds: 523
view_count: 2684
author: "The AI Automators"
description: |
  👉 Get ALL of our courses, systems and resources: https://www.theaiautomators.com/?utm_source=youtube&utm_medium=video&utm_campaign=tutorial&utm_content=cowork-scheduled-tasks
  
  Claude Cowork can now run real workflows on autopilot with its new scheduled tasks feature. You can set up recurring tasks that send daily status updates to Slack, generate weekly reports from files on your system or Google Drive, research topics on a schedule, organize files automatically, or even control your browser to do work on your behalf. All without writing a single line of code or deploying anything.
  
  In this video, I walk you through how scheduled tasks work in Claude Cowork, how to set them up, and how to configure them for different use cases. I also cover the key advantages and limitations, including how they compare to fully deterministic agentic workflows built with tools like Claude Code or other automation platforms.
  
  Scheduled tasks are extremely easy to create. You can either convert an existing Cowork task into a scheduled one or use the /schedule command to build one from scratch. Once created, each task stores a prompt that Cowork runs on your chosen schedule using whichever model you select, from Haiku for lightweight jobs to Opus for complex ones. Tasks can work from a designated folder, giving you a persistence layer between runs, and they self-heal thanks to the underlying agent harness.
  
  The trade-off is that these tasks only run while your computer is on and the app is open, the context resets each run, and because they rely on a probabilistic model rather than a fixed script, results may not be 100% identical every time. For purely deterministic, no-AI workflows, a coded solution or visual tool might still be the better fit. But for flexible, intelligent automation that would otherwise require significant setup, scheduled tasks are a very welcome addition.
  
  Chapters:
  0:00 - Overview
  1:34 - Creating a scheduled task
  2:11 - Scheduled task settings
  3:46 - Slash command
  4:29 - Pros
  5:34 - Cons
  8:17 - Verdict

yt_tags:
  []


# AI-enriched metadata
content_type: "Tutorial"
primary_topic: "AI Tools"
difficulty: "Intermediate"
audience:
  - "Engineers"
  - "Executives"
entities:
  companies:
    - "Google"
    - "Slack"
    - "Stripe"
  people:
    []
  products:
    - "Claude"
    - "Claude Code"
    - "Opus"
    - "Haiku"
  models:
    - "Claude Opus"
concepts:
  - "Your computer needs to be on when you're running them"
summary:
  - "# Claude Can Now Run 24/7 Without You (Scheduled Tasks)

Claude Co-work can now run real workflows on autopilot using their new schedule tasks feature"
keywords:
  - "ai-agents"
  - "ai-news"
  - "ai-tools"
  - "anthropic"
  - "claude"
  - "claude-code"
  - "coding"
  - "frameworks"
  - "google"
  - "haiku"
  - "opus"
  - "product-management"
  - "prompting"
  - "slack"
  - "stripe"
  - "tutorials"
  - "workflows"
---

# Claude Can Now Run 24/7 Without You (Scheduled Tasks)

Claude Co-work can now run real workflows on autopilot using their new schedule tasks feature. For example, it could send daily status updates to a Slack channel and integrate with a support ticketing system in the process. Or it could open up your browser and start doing work on your behalf. Or it could create reports and presentations directly on your file system. This is all handled by Claude Co's scheduled tasks feature. And while the interface might look pretty simple from here, it's actually pretty powerful when you dig into it. Up until now, we've been using co-work as an assistant. We get it to do something by sending it a prompt and then it goes off and does the work. But now, whenever you've identified a task that you want co-work to run on autopilot, you can ask it to create a schedule task for that, it will then appear within the schedule task window. And that could handle all sorts of tasks such as daily briefings where it integrates with your email and calendar and sends Slack notifications. It can create weekly reports from files on Google Drive or on your file system. It could do recurring research by researching topics online, analyzing competitors, or finding industry news. It could also organize files on your file system on a recurring basis or send your team updates on whatever channels required. In this video, I'm doing a quick walkthrough of how to set up and configure scheduled tasks within Cloud Co-work. And I'll also compare them against agentic workflows that you might create via AI coding agents like Claude Code. If you haven't watched my previous walkthrough video on clawed coowwork, I'd highly recommend you check that out. And if you want to get way ahead automating real work with AI, then check out our automators course in our community linked in the description below. So, what exactly is a scheduled task and how do you create one? I'll explain through an example. Let's say you open up a new task within Co-work and then ask it to give you the news, give you the most relevant AI news over the last two days. It will then search the web, search lots of different sources. There's a pretty comprehensive deep research type harness going on behind the scenes here. It does all of that and then goes through all of those and then gives us the most relevant news items based on that. So from there, you just ask it to create a new scheduled task. It might ask you a few clarifying questions, but the result of this is then a new scheduled task created within the scheduled section within co-work. To access the scheduled task screen, just open up the sidebar and select scheduled. And then from there, you'll be able to see any scheduled tasks you have. Let's click into this one that was created. So from there, you have a description already set. You have how often it repeats. You have any permissions that are allowed, such as sending Slack messages. And you can see the full prompt for this, and you can edit that however you want. For example, I've got it to only filter by the last 24 hours. And here are some important settings. You can decide which model you want to run for this. So if it's a complex task, then you can use Claude Opus, for example. If it's a pretty simple task, you could use cloth haiku and then your usage will go much further. When you're using that model, you can choose a folder for it to work from and it will then be able to view and edit files within that folder. You could even use that as a persistence layer where it could store data in between runs. Then for frequency, you can select manual, hourly, daily, weekday, or weekly. This was originally set as weekly, but I updated that to weekdays. And then you can set the time. You can also just manually click run now like this. and then it creates a new task. And now you can see it's created this separate task that it is now processing. In that example, I created a scheduled task from an existing task. So you could just be working away on a task and then realize, oh, this would be a very good candidate for a schedule task and then just get Claude to create one. You can also get cowwork to update previously created schedule tasks. So in this case, I got it to send the news update to a Slack channel. And then when I was happy with that, I asked it to update the schedule task to always send news items to the Slack channel. That's one way of creating a schedule task. Otherwise, you can use a slash command. So when you open up co-work, you can just type schedule slash schedule, select enter, and then from there add in whatever details you want to go to create that schedule task. Once the task is created, the prompt is effectively a stored skill behind the scenes. And then co-work just runs it on a schedule. From there it can connect to external systems or control your browser for example. And then from there it can output or action whatever it needs to. So these scheduled tasks can run unattended and in the background. But very importantly your computer needs to be on when you're running them. If your computer is asleep or if the app is closed when a task is scheduled to run, co-work will skip the task then run it automatically once your computer wakes up or you open the desktop app again. So, what is the good and bad of scheduled tasks and where do they fit within your overall automation stack? Well, first off, it's extremely easy to use and this is one of the biggest benefits. It should not be understated how these kind of tools massively reduce the barrier to entry of automating real work. Even though clawed code is very easy to use, it's still a technical step too far for a lot of people. And even if you are pretty technical, it is still a very handy option to be able to quickly turn out scheduled tasks like this. And also there's no deployment or extra configuration required. So once you've installed cloud co-work then scheduled tasks are just available by default as all of the tasks run with the agents chain of thought. It's extremely flexible which is a major advantage while also potentially being a disadvantage which I'll talk about later. Also following on from that the execution of these scheduled tasks are also self-healing because it's using the agent harness. It's using the AI's intelligence to execute it. So this is not like a Python script that just runs exactly the same every time. If it runs into errors, it can try again or fix them or change the approach depending on the context. The biggest downside currently is that these scheduled tasks only run when your computer is on. So if your computer is off, then the tasks get picked up the next time your computer is on and when the co-work app is running. Also, the context resets each run. So each scheduled task opens up as a new task within co-work which is both a good and bad thing because you won't get continuous pollution of the context each time it's run but also the next time it's run then it might not remember things that happened in the previous run. One solution to this is to get co-work to work within a folder and then you can get it to store its progress and implementation details in a file and then the next time that schedule task is run then it can read from that particular file. So you can still engineer context across runs in that regard. Also a negative or potentially a positive depending on how you look at it is that they're not fully deterministic. A deterministic workflow follows the same steps and works in the same way every time. For example, you could have a workflow created in a visual coding tool like NSN or a Python script created via cloud code and then this could listen out for new orders on your Stripe account and then deterministically create a new row on a Google sheet or send you an update via Slack or an email for example. These kind of workflows might not even include AI. These kind of procedural stepbased workflows have been running in business for decades. But of course AI can be used in certain parts of the process. But when you run a task in Claude Coowwork, it uses an advanced agent harness architecture behind the scenes. It can create a plan, progress through those as it's working through the tasks, and this can work in a loop for quite a while until it achieves a specific result. But these models are probabilistic. They might not always act in the exact same way. You can add skill files and improve your prompting to try to get it to act as consistently as you can, but it will not necessarily always act in the exact same way as a fully deterministic workflow. Also following on from that, if your workflows are purely deterministic, if you have an if then result, even if it's more complex than this, and if they do not need to use AI at all, then you could get clawed code or a visual workflow tool like nitn to create these kind of workflows and these will effectively run for free from then on. Whereas when using cloud co-work, it's going to use AI throughout the process. For some workflows, it might chew through a lot of tokens and the results might not be 100% consistent every time for all workflows. Also, Claude Co-work is still in a research preview phase, so you could run into issues running the app. Generally, these scheduled tasks have run fine for me. The only issue I really ran into was where the Claude model was overloaded, and it does not have automatic retries of the tasks in that case. So, that's definitely something to keep in mind. Overall, this is a very welcome feature within Co-work. It's probably been pretty heavily requested by users and it's a very viable way to create real agentic workflows without you having to dig into either workflow tools or AI coding agents. But if you want to go a level deeper then be sure to check out my video below on agentic workflows. If you want to get way ahead and get AI to automate real work, then check out our automators course in our community along with all of the other resources we have available
