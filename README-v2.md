# Forward Deployed Engineer (FDE) Roadmap

Three courses, taken in order. Each module lists topics, with tools in brackets.
Basics that an AI agent can teach or do are self-study. Each course ends with a project.

## Self-Study

Not taught in class. Learn these on your own or with an AI agent before Course 1.

- **Programming:** Python, TypeScript basics, Bash and Linux, Git (`uv`, `pytest`, `ruff`, `pydantic`, Node.js, `ssh`, `curl`, `jq`, GitHub)
- **Data and SQL:** SQL, vector search with HNSW and IVFFlat indexes, schema migrations, messy data, Base64 uses, image tools, warehouse basics (PostgreSQL, pgvector, DuckDB, pandas or Polars, Pillow, FFmpeg, ClickHouse, BigQuery)
- **APIs and backend:** REST and webhooks, auth basics, background jobs, polling and WebSockets, live chat and WebRTC, hosting models and their limits, reading API specs (FastAPI, `httpx`, Redis, Socket.IO, LiveKit, AWS Lambda, Cloudflare Workers, OpenAPI)
- **LLM fundamentals:** terminology, model types, open-source LLMs, model APIs, prompt and context design, cost and latency, failure modes (Hugging Face, Ollama, Anthropic SDK, OpenAI SDK, LiteLLM)
- **Retrieval (RAG):** document parsing, chunking, embeddings, hybrid search, reranking, vector storage, permissions-aware retrieval (Docling, Tesseract, OpenAI embeddings, Cohere Rerank, pgvector)

---

## Course 1: Sense and Solve

Goal: find real problems in a customer's data, solve them with agents, and prove the solution works.

### Module 1.1: Sensing Use Cases
- Exploring customer data with AI: schemas, volumes, quality (DuckDB, Claude Code, Metabase)
- Spotting use cases: manual steps, delays, duplicates, rework (SQL, pandas or Polars)
- Reading process evidence: tickets, emails, logs, documents (Docling, Claude Code)
- Sizing and ranking use cases: time or money saved against effort and risk (Google Sheets)

### Module 1.2: Data Storytelling
- Data storytelling: charts and narrative (Plotly or Matplotlib, Streamlit, Metabase)
- Action briefs: what to do, why, how much it saves (Markdown, Google Docs)
- Automated stakeholder emails and reports (Gmail API or Microsoft Graph, Slack or Teams webhooks)
- Measuring savings before and after (SQL, Metabase)

### Module 1.3: Agents and Tool Use
- Agent loops, tool design, agent vs plain workflow (raw SDK tool calling, Temporal)
- Model Context Protocol (MCP Python SDK, MCP Inspector)
- Intro to agent frameworks (LangGraph, Google Agent Development Kit)
- Human approval, guardrails, state and memory (Slack approval flows, LangGraph checkpoints, PostgreSQL or Redis)

### Module 1.4: Evals and Benchmarking
- Test sets from real customer cases (JSONL files, Langfuse datasets)
- Scoring: exact checks, LLM judges, human review (Promptfoo, Inspect AI, DeepEval)
- Benchmarking models: quality, latency, cost on your own test set (Promptfoo, Inspect AI)
- Regression tests in CI (`pytest`, Promptfoo, GitHub Actions)

**Project 1:** take a public business dataset, find at least ten use cases, solve three with agents, benchmark two models on them, and send each owner an action brief with the saving.

---

## Course 2: Production Engineering

Goal: ship the solution safely and keep improving it after launch.

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

### Module 2.3: Observability
- Tracing and monitoring (Langfuse, Arize Phoenix, OpenLLMetry)
- Inspecting network logs (browser DevTools, `mitmproxy`, `curl -v`)
- Provider logs and spend caps (OpenRouter activity logs, LiteLLM proxy budgets, Langfuse)

### Module 2.4: Run, Evolve and Present
- Agents that review logs and traces for issues and improvements (Langfuse, LangGraph, `cron`)
- Alerts and issue triage (Sentry, Slack webhooks)
- Improving from findings: prompts, tools, and pipelines, one change at a time (Git, GitHub Actions)
- Regression checks and rollback after every update (Promptfoo, `pytest`, Git tags)
- Live dashboards: usage, quality, cost, and savings (Metabase, Grafana, Streamlit)
- Presenting results to the customer: monthly report and review meeting (Plotly, Markdown, Google Slides)

**Project 2:** put one Project 1 solution into production: container, CI/CD, a security review of your own code, tracing, spend caps, and an agent that reviews its logs daily and opens issues, and a monthly results report for the customer.

---

## Course 3: Forward Deployment

Goal: take a solution from a first customer call to production inside their environment.

### Module 3.1: Discovery and Scoping
- Customer interviews and workflow mapping (Granola or Otter, Miro, Excalidraw, Mermaid)
- Scoping: problem statement and success metric (Notion or Google Docs, Linear or Jira)
- Rapid prototyping and demos (Streamlit, Next.js with Vercel, Claude Code)
- Cost and return estimates (Google Sheets, provider pricing pages)
- Writing: scope docs, status updates, decision memos (Markdown, Google Docs, Loom)

### Module 3.2: Enterprise Integration
- Systems of record (Salesforce, ServiceNow, SAP, SharePoint, Slack or Teams)
- SSO and identity: SAML, OIDC, SCIM (Okta, Microsoft Entra ID, WorkOS)
- Data pipelines (Airbyte or Fivetran, dbt, Airflow or `cron`)
- Legacy systems: SFTP drops, flat files, SOAP, on-prem databases (Paramiko, `zeep`, ODBC, SQL Server, Oracle)

### Module 3.3: Deploying in the Customer Environment
- Networking: VPC, private endpoints, VPN, firewalls, DNS, TLS (AWS VPC and PrivateLink, Tailscale or WireGuard, `dig`, `openssl`, nginx or Caddy)
- Infrastructure as code (Terraform)
- Managed containers (AWS ECS/Fargate, Cloud Run, Azure Container Apps)
- Security and compliance: SOC 2, GDPR, HIPAA, PII handling, audit logs (Microsoft Presidio, AWS CloudTrail, Vanta or Drata)
- Models through the customer's cloud (Amazon Bedrock, Azure AI Foundry, Vertex AI)

### Module 3.4: Ownership and Handoff
- Logging, metrics, and alerting (OpenTelemetry, Datadog, Sentry, Prometheus, Grafana)
- Production debugging with limited access (CloudWatch Logs, `psql`, `py-spy`, `tcpdump`)
- Runbooks, docs, customer training (Markdown, Confluence or Notion, Loom)
- Feedback to the product team (Linear or Jira, GitHub Issues, Slack)

**Project 3:** run a mock customer engagement end to end: discovery call, scope document, integration with one system of record, deployment with SSO, and a handoff runbook.

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
| **Sensing use cases in customer data** | 1.1 |
| **Base64 and image tools** | Self-study |
| **Data storytelling** | 1.2 |
| **Polling, live chat, WebRTC** | Self-study |
| **Hosting models and their limits** | Self-study |
| **Security review: finding auth and crypto bugs** | 2.2 |
| **Open-source LLMs** | Self-study |
| **Network logs, provider logs, spend caps** | 2.3 |
| **Agents that review their own logs** | 2.4 |
| **Model benchmarking** | 1.4 |
| **Cost and return estimates** | 3.1 |
| **Runbooks and customer training** | 3.4 |
