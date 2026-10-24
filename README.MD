<h1 align="center">Kishor Pant</h1>
<h3 align="center">Engineering Manager · Applied AI &amp; LLM Platforms</h3>

<p align="center">
  <a href="https://techtalkbyte.xyz"><img src="https://img.shields.io/badge/Website-techtalkbyte.xyz-0b7285?style=flat-square&logo=googlechrome&logoColor=white" alt="Website"></a>
  <a href="mailto:kishor@techtalkbyte.xyz"><img src="https://img.shields.io/badge/Email-kishor%40techtalkbyte.xyz-1b2f4b?style=flat-square&logo=maildotru&logoColor=white" alt="Email"></a>
  <a href="https://linkedin.com/in/mrkishorpant"><img src="https://img.shields.io/badge/LinkedIn-mrkishorpant-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
</p>

<p align="center">
  I build <b>production LLM systems that take real actions safely</b> — agentic workflows, MCP servers,
  RAG and human-in-the-loop guardrails on AWS Bedrock — while leading teams and staying hands-on in <b>Go</b> and <b>Python</b>.
</p>

---

## 🧭 At a glance

| | |
|---|---|
| **Role** | Engineering Manager — backend, infrastructure, AI platform and delivery |
| **Experience** | 10+ years across fintech &amp; payments, logistics, real-money gaming, drones and robotics, plus a co-founder stint |
| **Focus** | Agentic AI · Model Context Protocol · RAG · LLM evals · secure AI tooling |
| **Location** | Gurugram, India |

---

## 🚀 Products I've built and run

### 🛡️ [OpenRouting](https://openrouting.si) — SAST &amp; secrets scanning with AI triage that shows its work

> Proven open-source scanners find the issues; **Claude (via Amazon Bedrock)** removes false positives, explains each real issue in plain English and suggests a fix.

```mermaid
flowchart LR
    A[GitHub repo / website / API spec] --> B[Isolated scanner containers<br/>Semgrep · ZAP passive]
    B --> C[Normalize to SARIF-style Finding<br/>+ fingerprint dedup]
    C --> D[Secret redaction]
    D --> E[Claude on Bedrock<br/>21 specialist review agents]
    E --> F[Dashboard · PR comment · PDF report · MCP]
```

- **AI triage engine** — every finding gets a verdict, confidence score, explanation and patch. Findings are routed by scanner → CWE → rule keyword to one of **21 folder-driven specialist agents** (SQLi, SSRF, authz, crypto, supply chain, AI/agent security…); adding an agent is adding one Markdown file.
- **Remote MCP server** — query findings and start scans from Claude, ChatGPT or Claude Code. Built its own **OAuth 2.1 authorization server**: PKCE S256, dynamic client registration + client-ID metadata documents, rotating refresh tokens with reuse detection, per-grant rate limits, and human confirmation links for any write that hides a finding.
- **Agent-setup review** — inventories `CLAUDE.md`, `.claude/` settings, skills and MCP configs in a repo and reviews them for prompt-injection paths and over-broad tool permissions; can open a hardened setup PR.
- **Defence in depth** — scanners run with no network, non-root, read-only, all capabilities dropped; hardened git clone (no hooks/filters/submodules); SSRF guard with IP pinning for DAST; one shared redactor before every LLM call; prompt-injection-aware handling of all scanned content.
- **Platform** — PR-scoped reviews, passive DAST, API-suite analysis (Postman / OpenAPI / HAR / Insomnia / Bruno), credits ledger with refund-on-failure, Razorpay payments.

<sub><b>Stack:</b> Python 3.12 · FastAPI · Pydantic v2 · Celery + Redis · MongoDB (Beanie) · Docker SDK · Semgrep · OWASP ZAP · Anthropic SDK / AWS Bedrock · MCP · Next.js 16 + TypeScript · WeasyPrint · Nginx · Cloudflare</sub>

---

### 📈 [isaeo](https://isaeo.com) — SEO &amp; AEO analytics for agencies

> SEO asks *"will search engines rank this page?"* AEO asks *"will ChatGPT, Perplexity and Google AI Overviews **cite** it?"* isaeo scores both.

- **Full-site crawler** — follows internal links and streams results live over **Server-Sent Events**; falls back to a headless **Playwright** render for JavaScript-heavy pages.
- **AI search readiness score** — deterministic AEO analysis: JSON-LD types, FAQ / Q&amp;A blocks, answer-friendly structure, `llms.txt`, and whether GPTBot / ClaudeBot / PerplexityBot / Google-Extended are allowed in `robots.txt`.
- **Grounded AI agents** — Claude on Bedrock rewrites and prioritises fixes from facts the crawl already computed; every reply passes a **validator that drops anything not traceable to the input** — the guard against hallucination *and* prompt injection from crawled pages.
- **Keyword &amp; competitor research** — volume, difficulty, intent, CPC, competitor keywords and SERP analysis.
- **Agency workflow** — 0–100 health scoring, scheduled re-crawls, diffs between audits, white-label PDF reports, multi-tenant accounts, Razorpay billing with HMAC-verified upgrades, SES email.

<sub><b>Stack:</b> Python · Flask · MongoDB · BeautifulSoup + lxml · Playwright · AWS Bedrock (Claude) · WeasyPrint · croniter scheduler · Razorpay · Amazon SES · Docker · Gunicorn</sub>

---

## 🏢 Production AI at work

| System | What it does | Tech |
|---|---|---|
| **Agentic ops platform** (fintech) | Agents monitor payout health, investigate incidents through MCP tools and execute remediation — retry, provider switch, bulk payout — behind a policy engine that requires human approval | Bedrock · MCP · DBOS durable workflows · event-sourced audit · LLM-as-judge |
| **RAG support agent** (fintech) | Customer-facing answers from a curated knowledge base with per-answer confidence scoring and automatic human escalation; ops console for ingestion and session review | RAG · Bedrock · confidence scoring · escalation analytics |
| **Logistics MCP server** | 240+ platform APIs exposed as LLM-callable tools so developers and AI agents can integrate shipping directly | Go · Model Context Protocol |

<sub>Company code lives in private repositories — happy to walk through the architecture in a conversation.</sub>

---

## 🗺️ Career path

| Company | Domain | Role | Years |
|---|---|---|---|
| [ScopeX Money](https://scopex.money) | Stablecoin cross-border remittance | Engineering Manager | 2026 – now |
| [Shiprocket](https://shiprocket.in) | E-commerce logistics | Technical Lead | 2023 – 2026 |
| [QuizyGames](https://quizygames.com) | Real-money gaming | Core Team Member — Engineering | 2021 – 2022 |
| Immortal Technologies | Cloud web platforms | Senior Software Engineer | 2019 – 2020 |
| [ideaForge](https://ideaforge.com) | Drones / UAV | Technical Consultant | 2018 – 2019 |
| Medzipp | Health-tech | Co-Founder | 2017 – 2018 |
| [Milagrow HumanTech](https://milagrowhumantech.com) | Consumer robotics | Software Engineer | 2016 – 2017 |

**Domains I've shipped in:** 💸 fintech &amp; payments (ScopeX, Paylo payment gateway) · 🚚 logistics · 🎮 real-money gaming · 🛩️ drones · 🤖 robotics · 🏥 health-tech

---

## 🛠️ Tech stack

**AI &amp; LLM**<br>
![Claude](https://img.shields.io/badge/Claude-D97757?style=flat-square&logo=anthropic&logoColor=white)
![AWS Bedrock](https://img.shields.io/badge/AWS%20Bedrock-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white)
![MCP](https://img.shields.io/badge/Model%20Context%20Protocol-000000?style=flat-square)
![RAG](https://img.shields.io/badge/RAG-4B5563?style=flat-square)
![DBOS](https://img.shields.io/badge/DBOS-durable%20workflows-4B5563?style=flat-square)
![Vercel AI SDK](https://img.shields.io/badge/Vercel%20AI%20SDK-000000?style=flat-square&logo=vercel&logoColor=white)

**Languages**<br>
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**Backend &amp; Data**<br>
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=flat-square&logo=django&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-244c5a?style=flat-square)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat-square&logo=celery&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Debezium](https://img.shields.io/badge/Debezium%20CDC-91D443?style=flat-square)

**Cloud &amp; Ops**<br>
![AWS](https://img.shields.io/badge/AWS-ECS%20%C2%B7%20Lambda%20%C2%B7%20EventBridge%20%C2%B7%20SQS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Datadog](https://img.shields.io/badge/Datadog-632CA6?style=flat-square&logo=datadog&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat-square&logo=cloudflare&logoColor=white)

---

## 🧠 How I build AI systems

```text
1. Deterministic first   → scanners, crawlers and rules produce the facts
2. LLM second            → the model triages, explains and sequences — it does not invent
3. Validate the output   → schemas, tool calls and validators drop anything untraceable
4. Treat input as hostile→ redact secrets, fence untrusted content, assume prompt injection
5. Humans hold the key   → actions that move money or hide risk need explicit approval
```

---

<p align="center">
  <a href="https://techtalkbyte.xyz">techtalkbyte.xyz</a> ·
  <a href="mailto:kishor@techtalkbyte.xyz">kishor@techtalkbyte.xyz</a> ·
  <a href="https://linkedin.com/in/mrkishorpant">LinkedIn</a>
</p>
