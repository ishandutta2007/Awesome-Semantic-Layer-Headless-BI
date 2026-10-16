# Awesome-Semantic-Layer-Headless-BI

## Top Semantic Layer & Headless BI Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Governed Metric Definitions, Headless Serving APIs & AI-Ready Semantics*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Semantic Layer & Headless BI**. These tools define business metrics once — in code or a governed model — and serve them consistently to any consumer: BI dashboards, embedded analytics, natural-language AI agents, and custom applications. The semantic layer is the single source of truth for “what does revenue mean,” decoupled from any single visualization tool.

**Examples** include Looker, Cube, dbt Semantic Layer, AtScale, GoodData, Transform, MetricFlow, Lightdash, Snowflake Semantic Views, and Databricks Metric Views (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, headless serving APIs, and portable metric definitions — ideal for data teams prioritizing governance, avoiding semantic lock-in, and serving consistent metrics to AI and application consumers.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Looker (Google Cloud)](https://cloud.google.com/looker)**  
  **The enterprise BI platform built around LookML**, its centralized semantic modeling language . **LookML defines metrics, dimensions, and joins once** and drives every Explore, dashboard, and API query downstream . **Persistent Derived Tables (PDTs)** materialize expensive joins and aggregations so dashboards with hundreds of concurrent users read cached tables instead of re-running costly queries . **Open SQL Interface** exposes LookML models to Tableau, Power BI, Looker Studio, and Excel via JDBC — with the constraint that the LookML project must use a BigQuery connection . **AI accuracy**: Looker’s internal testing found its semantic layer **reduces data errors in GenAI natural-language queries by up to two-thirds** compared with letting models query raw tables directly . **Gemini in Looker** provides an analytical AI assistant that generates LookML from natural language . **Limitations**: Steep learning curve — practitioners describe “maintaining an entire code base just for analytics” . LookML’s consistency win stops at Looker’s boundary — it cannot tell whether the same metric is defined identically in other tools querying the same warehouse . Enterprise pricing typically starts around **$3,000–$5,000/month** for Standard Edition [citation:1][citation:3][citation:11].

- **[Cube Cloud](https://cube.dev/)**  
  **The headless BI serving layer for applications and embedded analytics.** **Cube Core is Apache 2.0, fully free, and self-hostable** — Cloud adds managed infrastructure, observability, and enterprise controls . **Pricing tiers**: **Free** (hobbyists, up to 5 workbooks), **Starter at $40/developer/month**, **Premium at $80/developer/month**, **Enterprise custom** . **Premium adds** Explorer and Viewer roles ($40 and $20/user/month respectively), embedded dashboards, 99.95% uptime SLA, and custom domains . **Enterprise adds** 99.99% SLA, **Bring Your Own Cloud (BYOC)**, **Bring Your Own LLM (BYOLLM)**, SAML SSO, and DAX API for Power BI . **Dedicated infrastructure** billed at $0.60–$1.20/hour depending on tier, with multi-cluster at $1.20/hour/cluster . **The clearest pattern for serving metrics to product APIs** — Cube is serving infrastructure, not a substitute for upstream modeling discipline . **Watch-out**: adds an extra infrastructure layer to operate [citation:2][citation:9][citation:10].

- **[dbt Semantic Layer](https://www.getdbt.com/product/semantic-layer)**  
  **Governed metrics defined in dbt, served through MetricFlow.** **MetricFlow is open-sourced under Apache 2.0** (October 2025, v0.209+) — the core engine is free . **dbt Cloud Starter at $100/developer/month** includes **basic Semantic Layer** with **5,000 queried metrics per month**; **Enterprise tiers scale** to **20,000** and beyond . **Query interfaces** include GraphQL and JDBC APIs, with downstream integrations for Tableau, Hex, Google Sheets, and Power BI (preview) . **dbt-native strength**: keeps semantic definitions **close to the dbt models that already govern transformation logic** — best fit when dbt is already central to your stack . **Watch-out**: MetricFlow’s open-source availability means you can self-host the engine, but the **Cloud service layer that coordinates queries and dispatches SQL is proprietary** — you lose the managed APIs and integrations [citation:1][citation:4][citation:9].

- **[AtScale](https://www.atscale.com/)**  
  **Universal semantic layer with virtual OLAP acceleration.** **Object-based consumption model** starting at roughly **$2,500/month** based on Deployed Semantic Objects (DSOs) . **2025 innovations**: **One-Click Modeling** scans source data to auto-identify metrics, dimensions, and relationships; **Composite Modeling** lets teams extend or inherit models without breaking the single source of truth; **Native PGWire support** enables plug-and-play compatibility with ThoughtSpot, Superset, and Sigma; **Native DAX and Tabular model support** in Power BI delivers live connectivity with no data duplication . **GenAI integrations** with **Databricks Genie and Snowflake Cortex Analyst** ensure AI-generated insights align with business definitions . **Ava (Ask, Verify, Answer)** intercepts ambiguous questions before computation — on the **BIRD-Interact benchmark, adding an AtScale semantic layer made an LLM twice as accurate**, with most of the lift coming from asking one clarifying question before running anything . **Open-source SML (Semantic Modeling Language)** : the industry’s first open language for defining, sharing, and operationalizing semantic models, with prebuilt TPC-DS, AdventureWorks, and Snowplow models and a developer SDK . **Best for enterprises wanting governed metrics across multiple BI tools** with AI-agent-ready APIs [citation:1][citation:5][citation:13].

- **[GoodData](https://www.gooddata.com/)**  
  **Composable, analytics-as-code platform with a headless BI engine.** **Semantic model as a universal metrics store** — metrics defined once, served via **declarative, open APIs** to any visualization app . **Platform fee starting around $1,500/month** based on workspaces and data scale (custom quote) . **Included in the 2024 Gartner Magic Quadrant for Analytics and BI Platforms**, recognized for its focus on the semantic layer as a universal metrics store and developer-first approach . **Headless vision**: GoodData’s analytics engine sits at the center of the modern data stack and directly queries cloud-stored data in real time, enabling “single source of truth metrics” that yield consistent results regardless of which front-end consumes them . **Best for embedded analytics and multi-tenant SaaS** needing governed metrics with API-first access [citation:6][citation:14].

- **[Transform (Acquired by dbt Labs)](https://transform.co/)**  
  **The original pioneer metrics store platform**, acquired by dbt Labs and integrated into the dbt Semantic Layer / MetricFlow ecosystem. **Standalone product retired** — accessible via dbt Cloud starting at $100/developer seat/month [citation:1].

- **[Omni](https://omni.co/)**  
  **Modern analytics and BI platform with a built-in semantic modeling layer.** Sales-led pricing starting from roughly **$1,000/month** for small teams. **14-day customized evaluation** available. Positioned as a more exploratory, point-and-click alternative to Looker’s code-heavy modeling [citation:1].

- **[Hex](https://hex.tech/)**  
  **Collaborative workspace combining notebooks, SQL, and metrics layer integrations.** **Professional at $36/editor/month**, **Team at $75/editor/month**, with **free viewer seats**. **Free Community plan**: 1 editor, 5 projects, 100 AI actions/month. Best as a **consumer of governed metrics** from Cube or dbt rather than a standalone semantic layer [citation:1].

- **[Snowflake Semantic Views](https://www.snowflake.com/)**  
  **Warehouse-native semantic definitions** within Snowflake’s control plane. **Single-platform lock-in is the trade-off** — governed metrics stay in Snowflake, but portability to other warehouses or BI tools is limited . Best for Snowflake-first teams wanting native governance without additional serving infrastructure [citation:9].

- **[Databricks Unity Catalog Metric Views](https://www.databricks.com/)**  
  **Governed YAML-defined metrics integrated with Unity Catalog and AI/BI.** Consumers include dashboards, Genie, and SQL users. **Single-platform lock-in** — metric definitions live in Databricks’ governance layer . Best for Databricks-first teams already centralizing governance in Unity Catalog [citation:9].

## Open-Source GitHub Projects

- **[Cube Core](https://github.com/cube-js/cube)**  
  **The leading open-source headless BI and semantic layer** — **Apache 2.0 licensed, 17,000+ GitHub stars** . **Rust-based serving layer** with caching and multi-tenant controls . **Serves metrics to applications, embedded analytics, and external consumers via API-first access** . The open-source core is fully self-hostable; Cube Cloud adds managed infrastructure and enterprise features . **The clearest pattern for serving governed metrics to product APIs** — Cube acts as serving infrastructure, not a replacement for upstream modeling discipline . **Watch-out**: adds an extra infrastructure layer to operate [citation:9][citation:16][citation:18].

- **[MetricFlow (dbt Labs)](https://github.com/dbt-labs/metricflow)**  
  **The open-source metrics engine powering the dbt Semantic Layer** — **Apache 2.0 licensed** . **Defines metrics and semantic models in dbt using the MetricFlow spec** and **generates SQL from configuration files** . **CLI support** for querying metrics, dimensions, and metadata . **Source-available version** includes metric definition and SQL generation; the **Cloud version adds JDBC/GraphQL APIs and downstream integrations** (Tableau, Hex, Google Sheets) . **Best for teams already modeling in dbt** who want governed metrics close to their transformation logic [citation:9][citation:12].

- **[Lightdash](https://github.com/lightdash/lightdash)**  
  **dbt-first BI with a metrics catalog and AI-facing documentation.** **Good consumer UX and cataloging** for business users . **Less suited for application-serving APIs** — it’s a BI consumer, not a headless serving layer . **Best for teams already modeling in dbt** who need a business-friendly metrics catalog, verified docs, and self-serve BI with AI/NLQ use cases [citation:9].

- **[semlayer](https://pypi.org/project/semlayer/)**  
  **The open-source semantic layer that infers itself** — skip the quarter of hand-writing dbt YAML . **Point it at your warehouse**: it profiles every column, discovers undeclared foreign keys, decodes status columns, finds business rules hiding in aggregate tables, and writes the whole thing down as an open, portable semantic layer **with confidence, provenance, and lifecycle on every claim** . **Ready for any AI agent to consume over MCP** . **The core problem**: frontier models solved only **21.3% of Spider 2.0’s enterprise-warehouse tasks** at publication — even today’s best agentic scaffolds reach ~30% . **On a messy-warehouse benchmark, an agent using the inferred layer answers 53% of business questions correctly vs 34% from raw schema (+54% relative)** — and it fixes the silent errors: raw-schema “total revenue” happily sums cancelled orders . **Cost**: ~$0.70 per 100 tables end-to-end with your own API key; **~80% of columns resolve from statistics alone** (LLM calls are escalation-only) . **`--no-llm` fully deterministic mode** still achieves 0.81 typing accuracy on messy fixtures . **`--no-sample-egress` prevents cell values from leaving for the LLM** at ~1 point of accuracy cost . **Read-only, minimal-grant** by design . **Review workflow**: `semlayer review layer.yaml` for accept/reject; **drift detection** catches schema changes in cron and CI . **The fastest path from existing warehouse to a governed, AI-consumable semantic layer** [citation:7].

- **[OrionBelt Semantic Layer](https://github.com/ralfbecher/awesome-business-intelligence)**  
  **Open-source semantic sidecar that compiles YAML semantic models to optimized SQL across 8 engines** (BigQuery, ClickHouse, Databricks, Dremio, DuckDB, MySQL, PostgreSQL, Snowflake) . **REST API, Arrow Flight SQL, and Postgres wire surfaces** . **Portable metric definitions** that travel across warehouses without lock-in . **Best for teams wanting governed semantics without being tied to a single engine** [citation:17].

### Additional Strong Open-Source Options

- **SLayer (semanticslayer)** — Semantic layer by Motley with YAML model definitions, formula support (cumsum, time_shift, change_pct, rank), and CLI/Python clients for querying governed metrics .
- **Apache Superset** — Open-source BI platform that can consume semantic layers and serve dashboards. Often paired with Cube or dbt for governed metrics [citation:1].
- **Metabase** — Open-source BI with models and metrics, though less formally governed than dedicated semantic layers.

**Frameworks for building custom systems**: Combine **Cube Core** for headless serving to applications and embedded analytics, **MetricFlow** for dbt-native governed metrics, **semlayer** for inferring a semantic layer from existing warehouses without hand-writing YAML, **OrionBelt** for portable definitions across multiple engines, and **Lightdash** for a business-friendly metrics catalog — to build a semantic layer architecture that serves consistent metrics to BI tools, product APIs, and AI agents without semantic lock-in.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Semantic layer tools differ significantly in deployment model, serving capability, and lock-in risk. **Cube is the clearest headless serving layer for applications and embedded analytics** . **dbt Semantic Layer keeps metrics close to transformation models** but its Cloud service layer is proprietary — only MetricFlow is open source . **Looker’s LookML consistency win stops at Looker’s boundary** — it cannot tell whether the same metric is defined identically in other tools querying the same warehouse . **AtScale’s Ava asks clarifying questions before computing** — on BIRD-Interact, adding a semantic layer made an LLM twice as accurate, most of the lift from asking before running . **Warehouse-native options (Snowflake Semantic Views, Databricks Metric Views) eliminate extra infrastructure** but create single-platform lock-in . **semlayer infers semantics from existing warehouses** — the fastest path from messy raw schemas to AI-consumable governance, with `--no-llm` and `--no-sample-egress` options for privacy-constrained environments . **AI agents without a semantic layer silently pick the wrong metric**: an agent asked for “revenue” against raw tables will sum cancelled orders without asking .
- Self-hosted open-source solutions require proper warehouse connectivity, metric model governance, and monitoring of serving latency and cache behavior.

---

**Made for data engineers, analytics engineers, platform teams, and developers building governed metrics and headless BI platforms.**  
Let's make semantic layers more open, portable, and AI-ready.
