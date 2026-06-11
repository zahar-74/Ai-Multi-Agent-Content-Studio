🎬 Multi-Agent AI Content Studio

Live Demo(https://img.shields.io/badge/Live_Demo-View_App-blue?style=flat-square&logo=google-cloud)](https://content-studio-zpv3q2nc3q-uc.a.run.app/)


Made with Google ADK(https://img.shields.io/badge/Built%20with-Google%20ADK-4285F4?style=flat-square&logo=google)](https://github.com/google/adk-python)

Live Application: [content-studio-zpv3q2nc3q-uc.a.run.app](https://content-studio-zpv3q2nc3q-uc.a.run.app/)

An AI-powered content creation platform where 9 specialized agents collaborate to generate a full package of marketing materials from a single topic. The system employs a three-phase pipeline (sequential, iterative loop, and parallel) to produce a blog post, social media content, email newsletter, and SEO metadata in approximately 10 seconds.

🏗️ System Architecture

The multi-agent workflow is composed of three distinct phases:
User Request



│
▼
┌────────────────────────────────────────────┐
│ Phase 1: Sequential │
│ ├── Topic Research Agent (Google Search) │
│ └── Content Drafter Agent │
└────────────────────────────────────────────┘



│
▼
┌────────────────────────────────────────────┐
│ Phase 2: Iterative Loop (max 2 cycles) │
│ ├── Quality Checker Agent │
│ └── Content Improver Agent │
└────────────────────────────────────────────┘




│
▼
┌────────────────────────────────────────────┐
│ Phase 3: Parallel Execution │
│ ├── Blog Post Writer Agent │
│ ├── Social Media Creator Agent │
│ ├── Email Newsletter Writer Agent │
│ └── SEO Metadata Agent │
└────────────────────────────────────────────┘



│
▼
Output Package (4 assets)


✨ Features

Intelligent Orchestration**: An orchestrator agent routes requests to either the content creation pipeline or a content analyzer agent.
Automated Quality Control**: A `LoopAgent` re-evaluates and revises content until a quality threshold is met.
Real-time Streaming**: Server-Sent Events (SSE) stream generated content from each agent as it completes.
Content Analysis Tool**: Analyze any provided text for word count, readability score, and generate relevant hashtags.

⚙️ Tech Stack

| Layer                 | Technology                            |

| Agent Framework       | Google Agent Development Kit (ADK)    |
| Foundation Model      | Gemini 2.5 Flash                      |
| Agent Deployment      | Google Cloud Vertex AI Agent Runtime  |
| Backend               | FastAPI (Python)                      |
| Frontend              | React                                 |
| Deployment            | Google Cloud Run                      |

🚀 Live Demo

Visit the live application: [Multi-Agent AI Content Studio](https://content-studio-zpv3q2nc3q-uc.a.run.app/)

Enter a topic, target audience, tone, and keywords to see the agent team generate a complete content package in real-time.

🧠 Key Technical Achievements

Parallel Agent Architecture: Independent agents for blog, social, email, and SEO run concurrently, reducing total generation latency from a sequential ~40 seconds to under 10 seconds.
Orchestrator Pattern: Uses an LLM-driven agent (`orchestrator_agent`) that transfers control to either the deterministic `full_content_workflow` or the `content_analyzer_agent` based on user intent.
Iterative Quality Loop: A `LoopAgent` runs a "check-and-improve" cycle, with `max_iterations` and an `exit_loop` tool to stop when quality criteria are met.

