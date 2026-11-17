# Forward Deployed Engineer (FDE) Roadmap

Three courses, taken in order. Each module lists topics, with tools in brackets.
The courses follow one loop: sense, solve, ship, deploy, evolve, and back to sense.

## How It Is Taught

- **Problems, not lectures.** Each problem is about 10x harder than a student could solve alone, so working with agents is a must.
- **Different people learn different things.** Across a portfolio of problems, most topics get covered.
- **Real problems.** Teams across the company supply the problems, so the work is close to a real engagement.
- **Evaluation:**
  - Leadership reviews each result at a glance
  - Solver-proof questions that agents alone cannot pass
  - The future as judge: predictions checked against what actually happens
  - Physical-world tasks, such as figuring out a device's behaviour from a phone connected to it

## Self-Study

Not taught. Learn these on your own or with an AI agent before Course 1.

- **Programming:** Python, TypeScript basics, Bash and Linux, Git (`uv`, `pytest`, `ruff`, `pydantic`, Node.js, `ssh`, `curl`, `jq`, GitHub)
- **Data and SQL:** SQL, vector search with HNSW and IVFFlat indexes, schema migrations, messy data, Base64 uses, image tools, warehouse basics (PostgreSQL, pgvector, DuckDB, pandas or Polars, Pillow, FFmpeg, ClickHouse, BigQuery)
- **APIs and backend:** REST and webhooks, auth basics, background jobs, polling and WebSockets, live chat and WebRTC, hosting models and their limits, reading API specs (FastAPI, `httpx`, Redis, Socket.IO, LiveKit, AWS Lambda, Cloudflare Workers, OpenAPI)
- **LLM fundamentals:** terminology, model types, open-source LLMs, model APIs, prompt and context design, cost and latency, failure modes (Hugging Face, Ollama, Anthropic SDK, OpenAI SDK, LiteLLM)
- **Retrieval (RAG):** document parsing, chunking, embeddings, hybrid search, reranking, vector storage, permissions-aware retrieval (Docling, Tesseract, OpenAI embeddings, Cohere Rerank, pgvector)

## Learn Elsewhere

Good material already exists for these. Learn there and come back; the courses focus on what is not built yet.

- [Tools in Data Science](https://tds.s-anand.net/): data tools, LLMs, deployment
- [The Missing Semester](https://missing.csail.mit.edu/): shell, Git, debugging
- [Hugging Face Agents Course](https://huggingface.co/learn/agents-course): agent basics
- [Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents): when to use agents and workflows
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) and [PortSwigger Web Security Academy](https://portswigger.net/web-security): security
- [Google SRE Workbook](https://sre.google/workbook/table-of-contents/): running systems in production

---

## Course 1: Sense and Solve

Goal: find problems nobody asked you to solve, solve them with agents, and prove the solution works.

### Module 1.1: Sensing and Initiative
- Thinking like a private investigator: every source worth checking, and what people hide or work around
- Internal sources: data, tickets, emails, chats, call transcripts, recordings (DuckDB, Docling, Whisper, Claude Code)
- External sources: research, company filings, news, reviews, job postings, competitor sites, public datasets (Playwright, Claude Code)
- Spotting use cases nobody asked for: manual steps, delays, rework, shadow spreadsheets, numbers that do not match across teams
- Sizing and ranking: time or money saved against effort and risk (Google Sheets)

### Module 1.2: Data Storytelling
- Data storytelling: charts and narrative (Plotly or Matplotlib, Streamlit, Metabase)
- Action briefs: what to do, why, how much it saves (Markdown, Google Docs)
- Automated stakeholder emails and reports (Gmail API or Microsoft Graph, Slack or Teams webhooks)
- Measuring savings before and after (SQL, Metabase)

### Module 1.3: Agents and Tool Use
- Agent loops, tool design, agent vs plain workflow (raw SDK tool calling, Temporal)
- Building tools and MCP servers for agents (MCP Python SDK, MCP Inspector)
- Intro to agent frameworks (LangGraph, Google Agent Development Kit)
- Human approval, guardrails, state and memory (Slack approval flows, LangGraph checkpoints, PostgreSQL or Redis)

### Module 1.4: Evals, Benchmarks and Load Tests
- Test sets from real customer cases (JSONL files, Langfuse datasets)
- Scoring: exact checks, LLM judges, human review (Promptfoo, Inspect AI, DeepEval)
- Benchmarking models: quality, latency, cost on your own test set (Promptfoo, Inspect AI)
- Load testing: how many users before it slows or breaks (k6, Locust)
- Regression tests in CI (`pytest`, Promptfoo, GitHub Actions)

**Project 1:** take a real business dataset plus outside sources, find at least ten use cases including some nobody asked for, solve three with agents, benchmark two models on them, and send each owner an action brief with the saving.

---

## Course 2: Production Engineering

Goal: ship the solution safely and know when it breaks.

### Module 2.1: Shipping Code
- Containers (Docker, Podman, Docker Compose)
- One cloud, core services only (AWS EC2, S3, RDS, IAM; or Azure equivalents)
- CI/CD (GitHub Actions)
- Secrets and config (`.env` with `pydantic-settings`, SOPS with `age`, Infisical or OpenBao)

### Module 2.2: Security Review
- Reading auth flows and spotting bugs: broken access control, IDOR, weak sessions, JWT misuse, leaked tokens (OWASP Juice Shop, jwt.io, `curl`, Keycloak)
- Crypto in practice: hashing, encryption, TLS handshake, certificates, SSH keys, and the mistakes that break them (`openssl`, `ssh-keygen`, `certbot`, `mitmproxy`)
- Finding bugs in code and config: secrets in repos, weak hashing, disabled certificate checks, open ports (Semgrep, Bandit, Gitleaks, Trivy, OWASP ZAP)
- LLM-specific bugs: prompt injection, tool permissions, data leaks (OWASP Top 10 for LLM Applications, Promptfoo red teaming)
- Reporting a finding: reproduce, impact, fix (Markdown, GitHub Issues)

### Module 2.3: Observability and Operations
- Tracing, logs, metrics, and alerts (Langfuse, OpenTelemetry, Prometheus, Grafana, Sentry)
- Inspecting network logs (browser DevTools, `mitmproxy`, `curl -v`)
- Provider logs and spend caps (OpenRouter activity logs, LiteLLM proxy budgets)
- Agents that review logs and traces and open issues (Langfuse, LangGraph, `cron`)
- Safe updates: regression checks and rollback (Promptfoo, `pytest`, Git tags)

**Project 2:** put one Project 1 solution into production: container, CI/CD, a security review of your own code, tracing, spend caps, and an agent that reviews its logs daily and opens issues.

---

## Course 3: Forward Deployment

Goal: deploy inside a customer's environment, then evolve and scale what you built.

### Module 3.1: Discovery and Scoping
- Customer interviews and workflow mapping (Granola or Otter, Miro, Excalidraw, Mermaid)
- Scoping: problem statement and success metric (Notion or Google Docs, Linear or Jira)
- Rapid prototyping and demos (Streamlit, Next.js with Vercel, Claude Code)
- Cost and return estimates (Google Sheets, provider pricing pages)
- Writing: scope docs, status updates, decision memos (Markdown, Google Docs, Loom)

### Module 3.2: Integration Problems
Taught through problems, not tools. Each problem gives a real system and a goal; the tools are hints.
- Sync a legacy system's nightly SFTP export into the CRM (Paramiko, Airbyte, dbt)
- Let staff sign in with their company account (Keycloak, SAML, OIDC, SCIM)
- Answer questions from an undocumented SOAP service and on-prem database (`zeep`, ODBC)
- Post agent results into Salesforce, ServiceNow, Slack, or Teams with approval (free developer instances)

### Module 3.3: Deploying in the Customer Environment
- Networking: VPC, private endpoints, VPN, firewalls, DNS, TLS (AWS VPC and PrivateLink, Tailscale or WireGuard, `dig`, `openssl`, nginx or Caddy)
- Infrastructure as code (Terraform)
- Managed containers (AWS ECS/Fargate, Cloud Run, Azure Container Apps)
- Security and compliance: SOC 2, GDPR, HIPAA, PII handling, audit logs (Microsoft Presidio, AWS CloudTrail, Vanta or Drata)
- Models through the customer's cloud (Amazon Bedrock, Azure AI Foundry, Vertex AI)

### Module 3.4: Own, Evolve and Scale
- Ownership and handoff: runbooks, docs, customer training (Markdown, Confluence or Notion, Loom)
- Unspoken needs: what users repeat, work around, or abandon without complaining (PostHog, OpenReplay, event logs)
- Acting before being asked: turn five clicks into one action, guess the next need from data
- Scaling: user groups, and what it takes to roll out from one business unit to all (SQL, Metabase)
- Closing the loop: the next app for this business unit, fed back into sensing (Module 1.1)
- Presenting results: monthly report and review meeting (Plotly, Markdown, Google Slides)

**Project 3:** run a customer engagement end to end: discovery, integration with one system of record, deployment with SSO, and handoff. Then study a month of usage, simplify one thing users repeat, and propose the next app.

**Every project has a wild card:** one idea nobody asked for, judged on how bold and useful it is.

---

## Deliberately Left Out

| Topic | Why it is skipped |
|---|---|
| Kubernetes, Helm, service mesh | Managed container services cover most deployments. |
| Training models from scratch, deep learning theory | FDEs use hosted models through APIs. |
| Fine-tuning | Prompting, retrieval, and evals solve most cases. |
| Advanced DSA | Useful for interviews only. |
| Hadoop, Spark internals, Kafka administration | Warehouses and managed pipelines have replaced them. |
| Microservice architecture patterns | Most deployments are one service plus integrations. |
| More agent frameworks | Two frameworks plus the raw API transfer everywhere. |
| Teaching basics agents can do | Covered in Self-Study. |

## How Our Roadmap Compares

Eight published roadmaps and job-posting studies were split into topics and checked against ours, self-study topics included.
Ours covers **167 of 209 topics, an 80% match**.

| Source | Topics covered | Match | Topics missing from ours |
|---|---|---|---|
| [Interview Kickstart job-posting analysis](https://interviewkickstart.com/blogs/articles/forward-deployed-engineer-skills-job-posting-analysis) | 12 of 13 | 92% | Domain expertise |
| [KDnuggets 7 steps](https://www.kdnuggets.com/7-steps-to-become-a-forward-deployed-engineer-in-2026) | 33 of 37 | 89% | Advanced DSA, GraphQL, Kubernetes, rollbacks and feature flags |
| [FullStack seven skills](https://www.fullstack.com/blog/the-seven-skills-that-define-a-forward-deployed-engineer) | 24 of 27 | 89% | GraphQL, Kubernetes, system design |
| [AI Agents Kit roadmap](https://aiagentskit.com/blog/how-to-become-forward-deployed-engineer/) | 25 of 31 | 81% | Go or Rust, gRPC, Kubernetes and Helm, air-gapped deployment, interview preparation, multi-region architecture |
| [Scaler tech stack](https://www.scaler.com/topics/forward-deployed-engineer-tech-stack/) | 24 of 30 | 80% | Java, MongoDB, Spark, air-gapped deployment, GraphQL, system design |
| [FDE Academy tech stack](https://fde.academy/blog/forward-deployed-engineer-tech-stack) | 21 of 29 | 72% | Java or Go, GraphQL, data quality checks, CrewAI, DSPy, fine-tuning, Kubernetes, Spark |
| [Scaler roadmap](https://www.scaler.com/topics/forward-deployed-engineer-roadmap/) | 14 of 21 | 67% | Advanced DSA, language internals, microservices vs monolith, event-driven systems (Kafka, RabbitMQ), gRPC, Kubernetes, air-gapped deployment |
| [FDE Academy skills](https://fde.academy/blog/forward-deployed-engineer-skills) | 14 of 21 | 67% | Java, GraphQL, NoSQL, Kubernetes, project management, business acumen, industry knowledge |

The match is highest against job-posting data. Percentages are approximate; the topic split is our own judgment.

### In other roadmaps, not in ours

| Topic | Sources listing it (of 8) | Our position |
|---|---|---|
| Kubernetes, Helm | 6 | Managed container services handle most deployments; two of the six call it good-to-know |
| GraphQL | 5 | Most enterprise systems expose REST and webhooks |
| System design, distributed systems | 4 | FDE work is mostly one service plus integrations; self-study and Module 3.3 cover the design skills needed |
| Java, Go, or Rust | 4 | Python and TypeScript lead job postings; the sources call the rest situational |
| Air-gapped and on-prem deployment | 3 | Limited to defence, government, and some finance customers |
| Advanced DSA | 2 | Helps in interviews, not in customer work |
| gRPC, Protocol Buffers | 2 | Customer integrations are almost always REST, files, or SQL |
| NoSQL (MongoDB) | 2 | PostgreSQL with JSON columns covers the same needs |
| Spark | 2 | Warehouses and DuckDB handle most FDE data sizes |
| Domain expertise, business acumen | 2 | Differs per industry, so it is learned on each engagement |
| Fine-tuning | 1 | Prompting, retrieval, and evals solve most cases |

### In ours, not in other roadmaps

| Topic | Module |
|---|---|
| **Sensing from many sources, with initiative** | 1.1 |
| **Base64 and image tools** | Self-study |
| **Data storytelling** | 1.2 |
| **Polling, live chat, WebRTC** | Self-study |
| **Hosting models and their limits** | Self-study |
| **Security review: finding auth and crypto bugs** | 2.2 |
| **Open-source LLMs** | Self-study |
| **Network logs, provider logs, spend caps** | 2.3 |
| **Agents that review their own logs** | 2.3 |
| **Acting on unspoken user needs** | 3.4 |
| **Scaling to other business units** | 3.4 |
| **Wild-card idea in every project** | Projects |
| **Model benchmarking and load testing** | 1.4 |
| **Cost and return estimates** | 3.1 |
| **Runbooks and customer training** | 3.4 |
