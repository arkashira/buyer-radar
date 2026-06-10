# ROADMAP.md – buyer‑radar

---

## Vision
Empower early‑stage AI startup founders with **actionable, data‑driven insights** into the most lucrative buyer segments, enabling faster go‑to‑market, higher conversion rates, and sustainable revenue growth.

---

## Milestones Overview

| Milestone | Target Release | Primary Goal | MVP‑Critical Items |
|-----------|----------------|--------------|--------------------|
| **MVP** | **2026‑07‑15** | Launch a usable, self‑service sales‑intel dashboard for a single AI product category (e.g., LLM‑based SaaS). | • Core data pipeline (signal ingestion → segment scoring)  <br>• Buyer‑Segment Identification UI  <br>• Exportable CSV/JSON report  <br>• Basic auth & tenancy isolation  <br>• Automated CI/CD & smoke tests |
| **v1 – Market‑Fit Expansion** | **2026‑10‑01** | Broaden coverage to multiple AI product verticals and add real‑time trend monitoring. | • Multi‑product taxonomy  <br>• Real‑time market trend feed  <br>• In‑app recommendation engine  <br>• Role‑based access control (founder, sales lead) |
| **v2 – Competitive Edge & Automation** | **2027‑02‑15** | Deliver competitive‑landscape analytics, pipeline automation hooks, and integrations with CRM tools. | • Competitive landscape module  <br>• Bidirectional sync with HubSpot/Close.io  <br>• AI‑generated outreach scripts  <br>• Usage‑based pricing & quota management |
| **v3 – Platform Scale & Ecosystem** | **2027‑07‑01** | Turn buyer‑radar into a SaaS platform for multiple startups, with marketplace extensions and white‑labeling. | • Multi‑tenant SaaS infra (K8s, Terraform)  <br>• Marketplace for third‑party data add‑ons  <br>• White‑label branding kit  <br>• Advanced analytics (cohort, LTV forecasting) |

---

## MVP – Must‑Have for Launch (2026‑07‑15)

| Area | Feature | Description | Acceptance Criteria |
|------|---------|-------------|---------------------|
| **Data Ingestion** | Signal Collector | Pull public & proprietary data sources (GitHub repos, Crunchbase, product reviews, funding rounds). | • Scheduler runs nightly <br>• Data stored in PostgreSQL + vector store (pgvector) <br>• >95% success rate on last 30‑day runs |
| **Core Engine** | Segment Scoring Model | LLM‑augmented classifier that scores buyer entities on *Fit*, *Intent*, *Budget*. | • F1 ≥ 0.78 on internal validation set <br>• Scores refreshed within 24 h of new data |
| **Backend API** | RESTful Endpoints | `/segments`, `/insights`, `/export`. | • OpenAPI spec generated <br>• 200 ms 95th‑percentile latency <br>• Auth via JWT |
| **Frontend** | Dashboard UI | Single‑page app showing top 5 buyer segments, key metrics, and downloadable report. | • Responsive (desktop & tablet) <br>• No more than 3 clicks to export CSV <br>• Usability test ≥ 4.5/5 |
| **Security & tenancy** | Basic Auth & Tenant Isolation | Each founder gets a unique workspace; data never leaks across tenants. | • Unit & integration tests for isolation <br>• OWASP Top‑10 compliance checklist passed |
| **Ops** | CI/CD Pipeline | GitHub Actions build, test, and deploy to staging; manual promotion to prod. | • 100% test coverage on core modules <br>• Deploy time ≤ 10 min <br>• Rollback script ready |
| **Documentation** | Quick‑Start Guide | README + inline docs for onboarding a new founder. | • New user can spin up a sandbox in ≤ 30 min |

---

## Phase 1 – Market‑Fit Expansion (v1) – Target Oct 2026

### Themes
1. **Vertical breadth** – support multiple AI product categories (LLM SaaS, Computer‑Vision APIs, Data‑Labeling tools).  
2. **Real‑time intelligence** – stream market events (funding, hiring spikes) to keep segments fresh.  
3. **Actionability** – embed recommendation engine that suggests next best actions per segment.

### Key Deliverables
| Theme | Feature | Ship By |
|-------|---------|---------|
| Vertical breadth | Taxonomy service + admin UI to add new product categories | 2026‑08‑15 |
| Real‑time intelligence | Kafka‑based event bus + WebSocket push to dashboard | 2026‑09‑01 |
| Actionability | “Next Steps” card with AI‑generated outreach suggestions | 2026‑09‑20 |
| UX | Role‑based UI (Founder vs. Sales Lead) | 2026‑09‑30 |
| Analytics | Segment growth heat‑map & churn predictor | 2026‑10‑01 |

---

## Phase 2 – Competitive Edge & Automation (v2) – Target Feb 2027

### Themes
1. **Competitive Landscape** – map rivals, pricing, feature gaps.  
2. **CRM Integration** – push insights directly into founders’ pipelines.  
3. **Automation** – generate outreach scripts and schedule follow‑ups.

### Key Deliverables
| Theme | Feature | Ship By |
|-------|---------|---------|
| Competitive Landscape | Data scrapers for competitor sites + comparative matrix UI | 2027‑01‑05 |
| CRM Integration | Bi‑directional sync connectors (HubSpot, Close.io, Pipedrive) | 2027‑01‑20 |
| Automation | Prompt‑to‑email generator with personalization tokens | 2027‑02‑01 |
| Pricing | Tiered usage‑based pricing model with quota enforcement | 2027‑02‑10 |
| Observability | Full‑stack tracing (OpenTelemetry) + alerting dashboard | 2027‑02‑15 |

---

## Phase 3 – Platform Scale & Ecosystem (v3) – Target Jul 2027

### Themes
1. **SaaS Multi‑Tenant Architecture** – fully isolated clusters, self‑service onboarding.  
2. **Marketplace** – allow third‑party data providers to sell enrichments.  
3. **White‑Label & Extensibility** – branding kits, plugin API.

### Key Deliverables
| Theme | Feature | Ship By |
|-------|---------|---------|
| SaaS Infra | Helm charts + Terraform scripts for automated tenant provisioning | 2027‑04‑15 |
| Marketplace | Marketplace UI + revenue‑share billing engine | 2027‑05‑30 |
| White‑Label | Theme engine + custom domain support | 2027‑06‑15 |
| Advanced Analytics | Cohort analysis, LTV forecasting, scenario simulation | 2027‑06‑30 |
| Compliance | SOC‑2 Type II audit readiness | 2027‑07‑01 |

---

## Success Metrics

| Metric | Target (MVP) | Target (v1) | Target (v2) | Target (v3) |
|--------|--------------|-------------|-------------|-------------|
| **Founders onboarded** | 25 | 100 | 300 | 1,000+ |
| **Monthly Active Users** | 20 | 80 | 250 | 800 |
| **Segment accuracy (F1)** | ≥ 0.78 | ≥ 0.82 | ≥ 0.86 | ≥ 0.90 |
| **Revenue (ARR)** | $50k | $250k | $1.2M | $5M+ |
| **Churn (founders)** | < 12% | < 10% | < 8% | < 5% |

---

## Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| Data quality / source reliability | Low‑quality insights → user distrust | Build source health monitor; fallback to cached baseline |
| Model drift as AI market evolves | Degraded segment scoring | Quarterly re‑training pipeline; automated drift alerts |
| Multi‑tenant security breach | Reputation & legal exposure | Zero‑trust networking; regular penetration testing |
| Integration fatigue (CRM connectors) | Slower adoption | Prioritize connectors with highest demand; provide SDK for custom adapters |
| Scaling costs (vector store, compute) | Cost overruns | Adopt autoscaling on GKE; use cost‑aware scheduling; negotiate volume discounts with cloud provider |

---

## Governance & Review Cadence

- **Weekly Sprint Review** – engineering leads present demo & burn‑down.
- **Bi‑weekly Product Council** – PM, PMM, and Founder‑Advocate review roadmap alignment.
- **Quarterly OKR Review** – measure against success metrics; adjust scope as needed.
- **Post‑Launch Retro** – after each major release (MVP, v1, v2, v3) to capture learnings.

---

*Prepared by the buyer‑radar product & engineering leadership team.*
