# Forward Deployed Engineer (FDE) Roadmap

Three courses, taken in order. Each module lists topics, with tools in brackets.

---

## Course 1: Engineering Foundations

Goal: build and ship a small backend service on your own.

### Module 1.1: Programming and Scripting
- Python: typing, async, packaging, testing (`uv`, `pytest`, `ruff`, `pydantic`)
- TypeScript basics (Node.js, `pnpm`, `tsc`, React)
- Bash and Linux command line (`ssh`, `curl`, `jq`, `grep`, `cron`, `systemd`)
- Git workflows and code review (Git, GitHub/GitLab)

### Module 1.2: Data and SQL
- SQL: joins, window functions, CTEs, query plans, indexes (PostgreSQL, `psql`, DBeaver)
- Vector search in SQL: HNSW and IVFFlat indexes (pgvector)
- Data modelling and schema migrations (SQLAlchemy, Alembic)
- Messy data: CSV, Excel, JSON, Parquet (pandas or Polars, DuckDB, `openpyxl`)
- Data storytelling: charts and narrative (Plotly or Matplotlib, Streamlit, Metabase)
- Base64 uses: binary in JSON, data URIs, images to LLMs (`base64` CLI, Python `base64`)
- Image tools: resize, convert, compress (Pillow, ImageMagick, FFmpeg, OpenCV)
- Warehouse basics (ClickHouse, DuckDB, BigQuery)

### Module 1.3: APIs and Backend
- REST design, webhooks, pagination, retries, idempotency (FastAPI, `httpx`, `tenacity`, Postman)
- Auth: API keys, OAuth 2.0, JWT (Authlib, PyJWT)
- Background jobs and caching (Redis, Celery or RQ)
- Polling, long polling, server-sent events, WebSockets (FastAPI, `EventSource`, Socket.IO)
- Live chat and WebRTC: signalling, STUN/TURN (LiveKit, Socket.IO, coturn)
- Hosting models and their limits: serverless, edge, containers, servers (AWS Lambda, Cloudflare Workers, Cloud Run, a VM)
- Reading API docs and specs (OpenAPI, Swagger UI, `openapi-generator`)

### Module 1.4: Shipping Code
- Containers (Docker, Podman, Docker Compose)
- One cloud, core services only (AWS EC2, S3, RDS, IAM; or Azure equivalents)
- CI/CD (GitHub Actions)
- Secrets and config (`.env` with `pydantic-settings`, AWS Secrets Manager, 1Password)
- Auth types and uses: Basic, API keys, bearer, sessions, OAuth 2.0, OIDC, SAML, mTLS, passkeys (`curl`, Keycloak, jwt.io)
- Cryptography basics: hashing, encryption, TLS handshake, certificates, SSH keys (`openssl`, `ssh-keygen`, `certbot`)

---

## Course 2: Applied AI Engineering

Goal: build an LLM feature that works on real data and prove that it works.

### Module 2.1: LLM Fundamentals
- LLM terminology: tokens, embeddings, transformers, encoder vs decoder, context window
- Model types: text, vision, multimodal, embedding, speech
- Open-source LLMs (Hugging Face, Ollama, llama.cpp)
- Model APIs: messages, streaming, structured output, tool calling (Anthropic SDK, OpenAI SDK)
- Prompt and context design, prompt caching (Claude Console workbench, OpenAI Playground)
- Cost, latency, token budgets, model choice (token counting APIs, LiteLLM, batch APIs)
- Failure modes: hallucination, refusals, truncation, prompt injection (Promptfoo red teaming, Guardrails AI)

### Module 2.2: Retrieval (RAG)
- Document parsing: PDFs, Office files, scans (Unstructured or Docling, Tesseract, AWS Textract)
- Chunking, embeddings, hybrid search, reranking (OpenAI embeddings, PostgreSQL full-text search, Cohere Rerank)
- Vector storage (pgvector first; Pinecone or Qdrant at scale)
- Permissions-aware retrieval (PostgreSQL row-level security, metadata filters)

### Module 2.3: Agents and Tool Use
- Agent loops, tool design, agent vs plain workflow (raw SDK tool calling, Temporal)
- Model Context Protocol (MCP Python SDK, MCP Inspector)
- Intro to agent frameworks (LangGraph, Google Agent Development Kit)
- Human approval, guardrails, state and memory (Slack approval flows, LangGraph checkpoints, PostgreSQL or Redis)

### Module 2.4: Evals and Observability
- Test sets from real customer cases (JSONL files, Google Sheets, Langfuse datasets)
- Scoring: exact checks, LLM judges, human review (Promptfoo, Inspect AI, DeepEval)
- Tracing and monitoring (Langfuse, LangSmith, or Braintrust)
- Regression tests in CI (`pytest`, Promptfoo, GitHub Actions)
- Inspecting network logs (browser DevTools, `mitmproxy`, `curl -v`)
- Provider logs and spend caps (OpenRouter, Anthropic and OpenAI usage dashboards, LiteLLM budgets)

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

## Capstone

Deliver one real workflow end to end, such as invoice processing: scope document, agent with retrieval,
eval results, containerized deployment with SSO, and a handoff runbook.

## How Our Roadmap Compares

Eight published roadmaps and job-posting studies were split into topics and checked against ours.
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
| System design, distributed systems | 4 | FDE work is mostly one service plus integrations; Modules 1.3 and 3.3 cover the design skills needed |
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
| **Base64 and image tools** | 1.2 |
| **Data storytelling** | 1.2 |
| **Polling, live chat, WebRTC** | 1.3 |
| **Hosting models and their limits** | 1.3 |
| **Cryptography, TLS handshake, SSH keys** | 1.4 |
| **Open-source LLMs** | 2.1 |
| **Network logs, provider logs, spend caps** | 2.4 |
| **Cost and return estimates** | 3.1 |
| **Runbooks and customer training** | 3.4 |
