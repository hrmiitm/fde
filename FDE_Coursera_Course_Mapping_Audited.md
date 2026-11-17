# FDE Roadmap × Coursera — Re-audited Course Mapping


## Coverage Summary

| Module | Coverage Estimate |
|---|---:|
| 1.1 Sensing and Initiative | **55%** |
| 1.2 Data Storytelling | **65%** |
| 1.3 Agents and Tool Use | **75%** |
| 1.4 Evals, Benchmarks and Load Tests | **70%** |
| 2.1 Shipping Code | **75%** |
| 2.2 Security Review | **65%** |
| 2.3 Observability and Operations | **60%** |
| 3.1 Discovery and Scoping | **65%** |
| 3.2 Integration Problems | **50%** |
| 3.3 Deploying in the Customer Environment | **55%** |
| 3.4 Own, Evolve and Scale | **45%** |

## Course 1: Sense and Solve

| Module | Coursera Courses — Verified Syllabus Topics | Combined Coverage | Remaining Gaps |
|---|---|---:|---|
| **1.1 Sensing and Initiative** | • [Business Process Discovery and Automation](https://www.coursera.org/learn/business-process-discovery-and-automation) — Process mining, event logs, rework, bottlenecks and automation opportunities.<br>• [Finding and Evaluating Market Intelligence](https://www.coursera.org/learn/finding-and-evaluating-market-intelligence) — Company filings, competitor websites, public sources, conflicting evidence and source verification.<br>• [Making the Case for Robotic Process Automation](https://www.coursera.org/learn/robotic-process-automation) — Automation candidates, risks, ROI, prioritization and proof of value. | **55%** | • Investigating internal tickets, emails, chats, calls and recordings together.<br>• Using agents to investigate mixed internal and external evidence.<br>• Proactively discovering problems without a supplied process or question. |
| **1.2 Data Storytelling** | • [Data Storytelling — DeepLearning.AI](https://www.coursera.org/learn/dlai-data-storytelling) — Narrative structure, evidence, memos, dashboards, notebooks and presentations.<br>• [Market Research Data: Dashboards and Storytelling](https://www.coursera.org/learn/market-research-data-dashboards-and-storytelling) — Dashboard design, metric validation and automated report scheduling.<br>• [AI Business Cases and ROI Models — IBM](https://www.coursera.org/learn/ai-business-cases-and-roi-models) — Baselines, savings, benefit measurement and decision-ready ROI cases. | **65%** | • Building actual Plotly/Streamlit or Metabase reporting applications.<br>• Automated stakeholder messaging via Gmail API, Microsoft Graph or Slack/Teams webhooks.<br>• End-to-end SQL-to-action-brief automation. |
| **1.3 Agents and Tool Use** | • [Agent Architectures and Production Deployment with LangGraph](https://www.coursera.org/learn/packt-agent-architectures-and-production-deployment-with-langgraph-rsqj8) — Tool calls, agent loops, state, human approval, checkpoints and error handling.<br>• [Developing MCP-Powered Agentic AI Systems](https://www.coursera.org/learn/developing-mcp-powered-agentic-ai-systems) — MCP architecture, servers, tools, resources and agent integration.<br>• [Generative AI with Python](https://www.coursera.org/learn/packt-generative-ai-with-python-dmeqw) — Modules 12–14: OpenAI Agents SDK, Google ADK and MCP client/server implementation. | **75%** | • Comparing raw model-SDK tool calls with durable workflows such as Temporal.<br>• Slack-based approval integrated into a working agent.<br>• Persistent checkpoint storage with PostgreSQL/Redis in the specified workflow. |
| **1.4 Evals, Benchmarks and Load Tests** | • [Mastering LLM Evaluation](https://www.coursera.org/learn/llm-evaluation-reliable-scalable-ai) — Versioned datasets, rules, LLM judges, human review, regression gates and CI/CD evaluation.<br>• [Deploying & Scaling Agentic AI: Testing & Observability](https://www.coursera.org/learn/packt-deploying-scaling-agentic-ai-testing-observability-c9ybe) — Task success, quality, latency, cost and automated benchmark pipelines.<br>• [JMeter Training for Beginners](https://www.coursera.org/learn/jmeter-training-for-beginners) — Load tests, concurrent users, request tests and performance scenarios. | **70%** | • Test sets from real customer cases and Langfuse datasets.<br>• Practical Promptfoo, Inspect AI or DeepEval.<br>• k6/Locust load-testing implementations.<br>• Full model-comparison and regression pipeline on company data. |

**Assessment:** Module 1.3 is a good match across several Coursera courses, including MCP and Google ADK. Module 1.1 needs internal practice because proactively spotting unknown problems is different from investigating an assigned question.

## Course 2: Production Engineering

| Module | Coursera Courses — Verified Syllabus Topics | Combined Coverage | Remaining Gaps |
|---|---|---:|---|
| **2.1 Shipping Code** | • [Intro to DevOps](https://www.coursera.org/learn/devops-intro) — Docker, images, volumes, Compose, GitHub Actions, CI/CD, deployment and rollback.<br>• [AWS Cloud Technical Essentials](https://www.coursera.org/learn/aws-cloud-technical-essentials) — EC2, S3, RDS, IAM, AWS compute and storage.<br>• [Container and Infrastructure Security Automation](https://www.coursera.org/learn/container-infrastructure-security-automation) — HashiCorp Vault, static/dynamic secrets and access policies. | **75%** | • `.env` configuration with `pydantic-settings`.<br>• SOPS/age, Infisical or OpenBao hands-on setup.<br>• Connecting all requirements in one complete AWS deployment. |
| **2.2 Security Review** | • [Application Security for Developers and DevOps Professionals — IBM](https://www.coursera.org/learn/application-security-for-developers-devops) — OWASP, TLS, OpenSSL, encryption, vulnerabilities and network scanning.<br>• [Container and Infrastructure Security Automation](https://www.coursera.org/learn/container-infrastructure-security-automation) — Semgrep, Gitleaks, Trivy, OWASP ZAP and CI/CD security checks.<br>• [AI Agent Security](https://www.coursera.org/learn/agent-security) — Prompt injection, broken access control, memory poisoning, tool boundaries and auditing. | **65%** | • Reproducing IDOR, weak-session and JWT implementation bugs.<br>• Certificate and TLS-handshake debugging with `openssl`/`mitmproxy`.<br>• Security review of actual repositories and configurations.<br>• Written findings covering exploit, impact and fix. |
| **2.3 Observability and Operations** | • [Monitoring and Observability — IBM](https://www.coursera.org/learn/monitoring-and-observability-for-development-and-devops) — Logging, tracing, OpenTelemetry, Prometheus, Grafana and monitoring.<br>• [Production LLM Monitoring & Optimization](https://www.coursera.org/learn/packt-production-llm-monitoring-optimization-4spsk) — Langfuse, LLM traces, tokens, cost analysis, dashboards and alerts.<br>• [Modern API Automation, From Postman to AI-Driven Pipelines](https://www.coursera.org/learn/packt-modern-api-automation-from-postman-to-ai-driven-pipelines-krigo) — DevTools Network tab, HTTP requests, API debugging, `curl` and HAR. | **60%** | • OpenRouter activity logs and LiteLLM spend caps.<br>• Agent that reviews Langfuse traces and creates GitHub issues.<br>• `mitmproxy` debugging.<br>• Promptfoo/pytest checks with safe updates and rollback. |

**Assessment:** 2.1 has good foundational coverage. The greatest gap in 2.3 is operating an automated feedback loop—not merely viewing monitoring dashboards.

## Course 3: Forward Deployment

| Module | Coursera Courses — Verified Syllabus Topics | Combined Coverage | Remaining Gaps |
|---|---|---:|---|
| **3.1 Discovery and Scoping** | • [Requirements Elicitation: Artifact and Stakeholder Analysis](https://www.coursera.org/learn/requirements-elicitation) — Stakeholder interviews, requirements, scenarios, storyboards and prototypes.<br>• [Production Deployment and Advanced Patterns](https://www.coursera.org/learn/production-deployment-and-advanced-patterns) — Rapid Streamlit agent interfaces, Flask APIs and deployment patterns.<br>• [AI Business Cases and ROI Models — IBM](https://www.coursera.org/learn/ai-business-cases-and-roi-models) — Feasibility, estimates, baselines, risks, ROI and business cases. | **65%** | • Rapid client demos with Next.js/Vercel and AI coding agents.<br>• Workflow mapping with Miro/Excalidraw/Mermaid.<br>• Customer status updates, scope documents and decision memos as part of one engagement. |
| **3.2 Integration Problems** | • [Source Systems, Data Ingestion, and Pipelines — DeepLearning.AI](https://www.coursera.org/learn/source-systems-data-ingestion-and-pipelines) — Source-system connectivity, batch ingestion, pipelines and database troubleshooting.<br>• [Cyber Security: Identity Access Management and Authentication](https://www.coursera.org/learn/cyber-security-identity-access-management-authentication) — Federation, SSO, SAML, OAuth, OpenID Connect and provisioning concepts.<br>• [Salesforce Integration With External Systems Part 1](https://www.coursera.org/learn/packt-salesforce-integration-with-external-systems-part-1-wsbea) — Salesforce SOAP/REST, authentication, CRUD, Postman and SOAP UI. | **50%** | • Nightly SFTP-to-CRM using Paramiko/Airbyte/dbt.<br>• Keycloak SSO setup and SCIM provisioning.<br>• Undocumented SOAP service with on-prem ODBC database.<br>• ServiceNow, Slack and Teams integrations with human approval. |
| **3.3 Deploying in the Customer Environment** | • [Amazon VPC Essentials](https://www.coursera.org/learn/amazon-vpc-essentials) — VPCs, routing, security groups, PrivateLink, endpoints, VPN and connectivity.<br>• [Infrastructure as Code and Monitoring](https://www.coursera.org/learn/infrastructure-as-code-and-monitoring) — Terraform, EC2 provisioning, resources, state, modules and infrastructure automation.<br>• [Deploy Your First Agent — Google Cloud](https://www.coursera.org/learn/deploy-your-first-agent) — Deploying ADK agents to Vertex AI Agent Engine and Cloud Run. | **55%** | • Integrating networking, Terraform and managed containers in one customer account.<br>• Full AWS ECS/Fargate or Azure Container Apps implementation.<br>• SOC 2, GDPR, HIPAA and PII-handling exercises with audit logs.<br>• Bedrock/Azure AI Foundry under customer identity and network controls. |
| **3.4 Own, Evolve and Scale** | • [Product Analytics for Prioritization & Data-Driven Decisions](https://www.coursera.org/learn/product-analytics-for-prioritization-and-data-driven-decisions) — Event tracking, funnel abandonment, friction, prioritization, churn logs and decision memos.<br>• [Digital Transformation and AI for Business — Wiley](https://www.coursera.org/learn/wiley-digital-transformation-and-ai-for-business) — Adoption, scaling, organizational change and KPIs. | **45%** | • Customer runbooks, technical handoff and training.<br>• PostHog/OpenReplay session analysis in a deployed application.<br>• Proactive improvements without customer requests.<br>• New application proposals informed by usage.<br>• Monthly customer outcome reports and review meetings. |

**Assessment:** Knowing SOAP, SAML, VPCs and Terraform in isolation is not equivalent to delivering an end-to-end client integration. Course 3 therefore needs the most realistic internal practice. Kubernetes, Helm and service meshes are **not** added as requirements.

## Recommended Delivery Model

| Approach | Modules | Rationale |
|---|---|---|
| **Coursera-led, with targeted labs** | 1.2, 1.3, 1.4, 2.1, 2.2 | Stronger syllabus alignment on foundational skills; supplement practical gaps. |
| **Blended Coursera + company exercises** | 1.1, 2.3, 3.1 | Research initiative, operations and client discovery require realistic situations. |
| **Company-led, project-based** | 3.2, 3.3, 3.4 | Enterprise integrations, customer deployment and long-term ownership are insufficiently covered by standalone courses. |

**Implementation note:** Assign relevant Coursera modules and lessons rather than all selected courses in full. Reuse overlapping lessons; avoid training on technologies outside the roadmap merely because a Coursera course contains them. Use the roadmap's three projects to verify applied skill.
