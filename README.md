<p align="center">
  <img src="assets/banner.svg" alt="Chris Timms, Head of Product. I build the systems my product teams run on. Agents read and draft. People decide." width="100%">
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/chris-timms-b0749996/"><img src="https://img.shields.io/badge/LinkedIn-Chris%20Timms-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://github.com/sirk-code87/portfolio"><img src="https://img.shields.io/badge/Portfolio-read%20the%20case%20files-0b1220?style=flat-square&logo=github&logoColor=white" alt="Portfolio"></a>
  <img src="https://img.shields.io/badge/Based%20in-UK-2dd4bf?style=flat-square" alt="Based in the UK">
</p>

Head of Product in hospitality commerce and payments. I build the systems my product teams run on: AI agents do the reading and drafting, and people make the decisions.

My [portfolio](https://github.com/sirk-code87/portfolio) documents systems I designed and shipped at a UK hospitality commerce company and, before that, at a restaurant ordering and payments platform. Each one covers the problem, how the system works, the decisions behind it, how it was built month by month, and what I'd do differently. The original systems and their code belong to those companies.

## Start here

<table>
<tr>
<td width="50%" valign="top">

### [pm-agent-os](https://github.com/sirk-code87/portfolio/tree/main/pm-agent-os)
The AI agent system I ran a product leadership role on: nine specialist lenses, a weekly report built only from logged facts, and a gate that holds every outgoing message for my approval.

<sub>1,177 decision records · 4,470 logged work events · nine months in daily use</sub>

</td>
<td width="50%" valign="top">

### [account-ops-console](https://github.com/sirk-code87/portfolio/tree/main/account-ops-console)
A tool I built during a payments incident that grew, in about five weeks, into the operations team's console for every merchant payment account.

<sub>Stripe Connect · threat-modelled first write · fail-closed audit log</sub>

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [insight-coach](https://github.com/sirk-code87/portfolio/tree/main/insight-coach)
A two-to-three question chat that turns "something I noticed" into an evidenced product insight, credited to the customer and the colleague who raised it.

<sub>Web, Slack and embedded in internal tools · evaluation harness</sub>

</td>
<td width="50%" valign="top">

### [insight-relay](https://github.com/sirk-code87/portfolio/tree/main/insight-relay)
One intake for about ten feedback sources. People confirm what they file; automated sources pass an AI judge and a trial run before anything reaches the roadmap.

<sub>96% accuracy on hand-checked call notes · every lane starts in dry-run</sub>

</td>
</tr>
</table>

**[Product case studies](https://github.com/sirk-code87/portfolio/tree/main/product-case-studies)**: product decisions told as problem, solution and impact. Start with [Retuning fraud rules that were turning away good guests](https://github.com/sirk-code87/portfolio/tree/main/product-case-studies/fraud-rules-blocking-good-guests): a reversible call made live, measured against triggers agreed in advance. More are being added.

## How the pieces fit

What customers and colleagues notice becomes evidence on the product roadmap. The roadmap becomes small code changes that an engineer reviews. The agent system runs the loop and stops for a person at every step that can't be undone.

```mermaid
flowchart LR
    subgraph signals["What people notice"]
        staff["Colleagues<br/>on the web, in Slack,<br/>inside internal tools"]
        auto["Surveys, call transcripts,<br/>support tickets, email,<br/>in-app feedback"]
        crm["Customer records<br/>in the CRM"]
    end

    subgraph intake["Intake"]
        coach["insight-coach<br/>a short guided chat;<br/>the person confirms"]
        relay["insight-relay<br/>routes every source<br/>to the roadmap"]
    end

    subgraph roadmap["Roadmap"]
        pb[("Productboard<br/>evidence and features")]
    end

    subgraph delivery["Delivery"]
        issues["Small, well-defined<br/>tasks"]
        runner["Overnight agent run<br/>drafts the code change"]
        human{{"An engineer reviews<br/>and approves"}}
    end

    subgraph ops["Operations"]
        console["account-ops-console<br/>payment account<br/>management"]
    end

    staff --> coach --> relay
    auto --> relay
    crm -->|"daily sync"| relay
    relay -->|"notes linked to<br/>customer and source"| pb
    console -->|"feedback button"| coach
    pb --> issues --> runner --> human
    human --> shipped(["Fix goes live"])

    os["pm-agent-os<br/>the agent system<br/>that runs the loop"]
    os -.->|"runs"| relay
    os -.->|"runs"| runner
    os -.->|"reports on"| pb

    classDef mine fill:#134e4a,stroke:#2dd4bf,stroke-width:2px,color:#f8fafc
    classDef gate fill:#fbbf24,stroke:#b45309,color:#0b1220
    class coach,relay,console,os mine
    class human gate
```

<sub>Teal: systems documented in the portfolio. Amber: where a person decides.</sub>

## How I work

- **Agents draft; a person decides.** Every outgoing message and publication waits for my approval, and every code change starts as a proposal an engineer can review.
- **Facts first.** Facts are recorded as the work happens, so every claim in a report traces back to a record.
- **Decisions on paper.** Every decision is written down with who made it, when, and how easily it can be reversed.
