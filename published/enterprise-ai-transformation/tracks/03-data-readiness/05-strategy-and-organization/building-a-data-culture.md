---
type: Concept
title: Building a Data Culture
description: How to build the organizational environment where data-backed decisions are routine, data quality is everyone's accountability, and infrastructure actually gets used.
tags: [data-culture, change-management, data-literacy, governance, adoption]
timestamp: "2026-06-12"
---

## Why This Is the Hard Part

The technology works. The frameworks exist. The tools are available. Organizations that fail at AI data readiness almost never fail because the technology wasn't there.

They fail because people didn't use it, didn't trust it, didn't own it, or worked around it when it created friction. The technical investment produces infrastructure. Culture determines whether that infrastructure gets used.

Data culture is the organizational environment where decisions are routinely backed by data, where data quality is everyone's accountability rather than one team's burden, and where problems are surfaced and fixed rather than hidden. Without it, even the most sophisticated data infrastructure becomes shelfware.

> **90%** of directors and managers say company leaders are not paying adequate attention to bad or inaccurate data ([Qlik, 2025](#ev-qlik-data-quality-ai-2025-leadership-attention))

> **85%** believe leadership isn't addressing data quality issues ([Qlik, 2025](#ev-qlik-data-quality-ai-2025-not-addressed)), despite **81%** of companies still having significant data quality problems ([Qlik, 2025](#ev-qlik-data-quality-ai-2025-significant-issues))

> BCG's **10-20-70** rule: AI success comes 10% from algorithms, 20% from technology and data, and **70% from people and process** ([BCG, 2024](#ev-bcg-2024-ten-twenty-seventy))

The pattern in every one of these stats is the same: the people closest to the work can see the data-quality gap, and closing it depends on leadership creating the conditions to act on it — not on more technology.

---

## The Four Elements That Actually Drive Data Culture

Research and field experience consistently point to the same four elements in organizations where data culture is real rather than declared. These aren't abstract principles — each one has specific, observable behaviors that distinguish organizations that have it from organizations that say they do.

### 1. Executive Leadership That Visibly Uses Data

Data culture cannot be mandated from the middle. It requires executives who visibly use data in their own decisions — not executives who say data matters while making decisions by intuition.

The specific behaviors that matter:

- Asking "what does the data say?" before approving a strategic decision
- Citing data in public communications and all-hands meetings
- Funding data literacy programs and protecting that budget when pressures arise
- Holding direct reports accountable for data product quality within their domains
- Treating data quality failures as business problems, not IT problems

HBR authors Davenport and Mittal are direct about this: the single biggest barrier to becoming data-driven is the lack of executive leadership that visibly values data and analytics. Governance programs, literacy investments, and quality infrastructure all stall without behavioral modeling from the top.

### 2. Data Literacy Distributed Across All Roles

Data literacy is not a skill for data practitioners. In a functioning data culture, every employee can read and interpret data relevant to their role, make basic data-informed decisions, and recognize when they're looking at something suspicious.

Literacy operates at three levels:

**Foundational** (every employee) — read charts and dashboards, understand basic concepts like averages and trends, recognize data quality red flags, make simple data-informed decisions in day-to-day work.

**Applied** (business analysts, operations leads, domain managers) — query data systems, build basic analyses, interpret model outputs, identify AI opportunities within their domain, challenge AI recommendations with appropriate skepticism.

**Advanced** (data scientists, ML engineers, AI practitioners) — full technical capability to build, evaluate, and govern AI systems.

Most organizations invest heavily at the advanced tier and neglect the applied tier. This is the wrong priority. A model no business team trusts or understands produces no value. The applied tier — analysts and managers who can translate between business problems and data — is consistently the highest-leverage and most underdeveloped.

### 3. Governance That Enables Access

Data culture breaks when people want to use data but cannot get to it. Complex access request processes, slow approval queues, and opaque permissions teach people to work around data systems rather than through them. A spreadsheet they control beats a data product they can't access.

The tension is real: ungoverned access creates risk. But governance programs that prioritize restriction over enablement are culture killers. Every governance policy should be evaluated against a simple question: does this make it easier or harder for people to use data correctly?

Practical mechanisms that build culture through access:

- Self-serve catalog access for analysts — no ticket required to browse and discover
- Role-based access that grants appropriate permissions by default rather than requiring individual approvals
- Data products with enough documentation that consumers can assess fitness without contacting the producer
- Quality signals surfaced in the catalog so consumers can make informed decisions before using data

### 4. Accountability That Builds Trust

People trust data that is reliable, owned, and honestly documented. They stop trusting data that surprises them with errors, has no clear owner to call when something's wrong, or is presented as higher quality than it actually is.

Trust is built through:

- Consistent quality — data that is reliable over time earns trust gradually. This is why continuous quality monitoring matters beyond governance compliance.
- Transparency about known limitations — a data product with documented known issues is more trustworthy than one presented as perfect. Honesty about limitations signals that quality is actively managed.
- Named ownership — when consumers know who is accountable for a dataset, they have someone to hold accountable and someone to contact. Anonymous ownership means no accountability.
- Fast incident response — an MTTR measured in hours builds more trust than one measured in weeks. How quickly problems are resolved signals how much the organization cares about data quality.

---

## Why Culture Change Programs Fail

Most data culture initiatives don't fail because the approach was wrong. They fail because they're underfunded, owned by the wrong team, or never connected to how people are actually evaluated.

**Declared without being funded.** Leadership announces "we are becoming data-driven" without allocating budget for training, tooling, change management, or the engineering capacity that data product ownership requires of domain teams. Declarations without resources produce cynicism faster than any other outcome.

**Data team as culture owner.** The data team cannot own data culture any more than the IT team can own digital transformation. Culture is organizational. Data culture requires changes in how every business function operates. When it's owned by the data team, it becomes a program the data team does to other people, which doesn't work.

**Training without workflow change.** Literacy programs that teach employees to read dashboards but don't change the decision processes those employees participate in produce no behavioral change. Training must be paired with changes to how decisions are actually made.

**Measuring activity, not behavior.** Programs that report training completion rates without measuring whether decisions are actually more data-informed have no feedback loop. "We trained 500 people" is not evidence that culture changed.

---

## What Actually Works

**Data ambassadors.** Gulf Bank assembled a network of data-literate employees distributed across business units — people respected by their peers who help colleagues see the value of data and develop a shared vocabulary. Peer-to-peer cultural transmission is faster and more durable than top-down mandates.

**Embedding data in workflows.** Literacy sticks when people apply new skills immediately in their actual work. Surface quality signals in CRM workflows. Add data context to approval processes. Provide real-time KPI visibility in operational tools. Learning through doing, in real work, is more effective than classroom training.

**Visible early wins.** Nothing builds data culture faster than a concrete example where a data-informed decision produced a better outcome than the previous approach. Find the early wins, document them with specifics, and communicate them broadly. The stories spread the culture faster than any program.

**Measuring behavior, not activity.** Define 3–5 behavioral indicators that data culture exists. What percentage of strategic decisions include data-backed justification? How often does leadership ask for evidence before approving initiatives? How many business units submitted AI use case proposals last quarter? Track these alongside technical metrics.

---

## The Data Culture Maturity Model

| Level | Name | What it looks like |
| --- | --- | --- |
| 1 | Data-Unaware | Data used only by analysts. Business decisions made by intuition and seniority. Quality problems invisible to leadership. |
| 2 | Data-Aware | Some teams use dashboards. Quality recognized as a problem. Literacy programs initiated but not scaled. Leadership uses data selectively. |
| 3 | Data-Informed | Most decisions supported by data. Business teams can access and interpret data. Quality tracked. Some ownership accountability in place. |
| 4 | Data-Driven | Data-backed decisions are the norm. Applied practitioners in all business units. Governance enables access. All critical data assets have named owners. |
| 5 | Data-Native | AI and data embedded in every business process. Continuous improvement culture. Data quality is a competitive advantage. Culture self-reinforces. |

Most enterprises are between Level 2 and Level 3. The move from Level 3 to Level 4 — making data-backed decision-making the organizational norm rather than the exception — typically requires 2–3 years of sustained effort and is the hardest cultural transition in the readiness journey.

---

## Practical Implementation Steps

**Step 1: Baseline before investing.** Run a culture assessment before designing programs. How do people currently make decisions? Where does data sit in those processes? What are the specific access barriers? What is the trust level in existing data? The baseline shapes what intervention is needed.

**Step 2: Find and invest in ambassadors.** Identify data-literate people in each business unit who are respected by their peers. Give them platform, resources, and recognition. Ambassador networks scale culture faster than any top-down program because they work through trusted peer relationships.

**Step 3: Fix the highest-friction access points.** Audit the data access process from a business user's perspective. How many steps does it take to get to a dataset they need? Where do people give up and use a spreadsheet instead? Fix those points first. Every friction point is a culture tax.

**Step 4: Design literacy programs around actual decisions.** Training should be built around the real decisions each role makes — not abstract data skills. A marketing manager's program should cover how to interpret attribution data, not how data warehouses work.

**Step 5: Audit governance for culture impact.** Review every governance policy for whether it enables or restricts correct data use. Eliminate friction without compliance rationale. Automate controls that currently require manual approval. Every unnecessary obstacle to correct data use is an obstacle to data culture.

**Step 6: Measure behavioral change.** Define the behavioral indicators upfront. Track them quarterly. Report them to leadership alongside technical metrics. If the indicators aren't moving, the program isn't working — and you'll know before you've spent years on the wrong approach.

These six steps are not a one-time program. They are a feedback loop. Culture changes slowly and non-linearly — it plateaus, backslides when leadership changes, and accelerates when a visible win lands at the right moment. The organizations that succeed treat culture change as an ongoing operational practice, not a project with a completion date.

---

## Readiness Checklist

- [ ] Executive sponsor identified with P&L accountability and visible data-using behavior
- [ ] Data literacy levels defined per role category — foundational, applied, advanced
- [ ] Literacy program designed around actual job decisions, not abstract skills
- [ ] Data ambassador network identified and invested in — one per major business unit
- [ ] Data access friction audited — highest-friction points identified and being addressed
- [ ] Governance policies audited for enablement vs. restriction — unnecessary friction being eliminated
- [ ] Early wins identified, documented, and communicated broadly
- [ ] Behavioral culture metrics defined — not just training completion rates
- [ ] Change management resourced as a first-class workstream — most AI value comes from people and process, not algorithms ([BCG, 2024](#ev-bcg-2024-ten-twenty-seventy))
- [ ] Domain team KPIs updated to include data product quality accountability
- [ ] Culture maturity level assessed and target level defined with a realistic timeline
- [ ] CDAO or equivalent has organizational change mandate, not just a technical one

---

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Qlik — *Data Quality is Not Being Prioritized on AI Projects (survey of 500 U.S. AI professionals, fielded Feb 2025)*, 2025.** 90% of data professionals at the director or manager level agree that company leaders are not paying adequate attention to bad or inaccurate data. [View source](https://www.qlik.com/us/news/company/press-room/press-releases/data-quality-is-not-being-prioritized-on-ai-projects){#ev-qlik-data-quality-ai-2025-leadership-attention} · verified 2026-06-21 · primary
- **Qlik — *Data Quality is Not Being Prioritized on AI Projects*, 2025.** 85% believe leadership isn't addressing these data quality issues. [View source](https://www.qlik.com/us/news/company/press-room/press-releases/data-quality-is-not-being-prioritized-on-ai-projects){#ev-qlik-data-quality-ai-2025-not-addressed} · verified 2026-06-21 · primary
- **Qlik — *Data Quality is Not Being Prioritized on AI Projects*, 2025.** 81% of AI professionals say their company still has significant data quality issues. [View source](https://www.qlik.com/us/news/company/press-room/press-releases/data-quality-is-not-being-prioritized-on-ai-projects){#ev-qlik-data-quality-ai-2025-significant-issues} · verified 2026-06-21 · primary
- **BCG — *Where's the Value in AI?*, 2024.** AI leaders follow the rule of putting 10% of their resources into algorithms, 20% into technology and data, and 70% into people and processes. [View source](https://www.bcg.com/publications/2024/wheres-value-in-ai){#ev-bcg-2024-ten-twenty-seventy} · verified 2026-06-20 · primary
