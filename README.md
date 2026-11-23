# Peter Fischer

**AI operations for logistics and process work: governed workflows, verifiable artifacts, human accountability.**

I come from temperature-controlled logistics: warehouse processes, picking, staffing constraints and cold chain risk.
I build AI workflows for that kind of work. A workflow takes messy operational input, produces a defined work product,
and leaves evidence that it stayed inside an agreed boundary.

---

## How the projects fit together

| Layer | Project | Role | Repository |
|---|---|---|---|
| Method | **IntoKI OS** (formerly GosseOS) | How work is classified, routed to a working mode, built and reviewed | [gosseos-framework](https://github.com/fissafissaintoki/gosseos-framework) |
| Knowledge | **KnowledgeOS** | Registry for artifacts, canonical terms, drift reports and audit records | [knowledgeOS-app](https://github.com/fissafissaintoki/knowledgeOS-app) |
| Application | **Prompterator** | Web app that turns raw input into structured artifacts and dossiers | [operator-fischer-proof-of-work-demo](https://github.com/fissafissaintoki/operator-fischer-proof-of-work-demo) |
| Runtime | **KYRON** | Governed runtime and public release channel with verified releases | [Kyron-runtime-public](https://github.com/fissafissaintoki/Kyron-runtime-public) |

The operating chain behind all four:

```text
raw input → problem class → working mode → artifact → verification → reusable knowledge
```

---

## Evidence

What you can check in the repositories yourself:

**Prompterator** (Python, OpenAI + Anthropic APIs, ReportLab)
- Two models draft independently, then the drafts are merged. Contradictions are marked as assumptions instead of being silently resolved.
- If a provider fails, the response says so. A partial run is never reported as a complete synthesis.
- About 150 unit tests in `tests/`, run in GitHub Actions on every push and pull request.
- A command safety gate for coding agents, with rules, test cases and a coverage report (`tools/command-safety-gate/`).

**KYRON** (Python, GitHub Actions, MCP)
- Release payloads are checked against generated manifests before deployment (`scripts/verify_release.py`, `schemas/`).
- Tests for the release verification and the public offer (`tests/`).
- A documented trust model, security policy and rights notice (`docs/TRUST_MODEL.md`, `SECURITY.md`, `RIGHTS.md`).
- A read-only MCP endpoint for deterministic planning and metadata checks.

**KnowledgeOS** (YAML registry, Markdown records)
- An artifact schema, a register of canonical and deprecated terms, and a source registry (`registry/`).
- Dated proof runs, drift reports and audit records (`reports/`).
- Release, risk and verification policies (`governance/`).

**IntoKI OS** (Markdown specification, FastAPI and React workbench prototype)
- Mode specifications, a governance gate and an artifact standard.
- Logistics case: cold chain risk analysis (`cases/LOGISTICS_COLD_CHAIN_RISK_CASE.md`).
- A workbench prototype with routing, integrity check and artifact registry (`workbench/`).

---

## Domain focus

- Cold chain and temperature-controlled warehousing
- Picking processes, including a wearable picking concept with a risk assessment (GlowGlove)
- Operational risk, process audits and decision support
- Governance for AI use: assumptions, verification gates, human approval

---

## Working principles

1. **The human owns the result.** AI prepares and checks. It does not decide.
2. **Claims need a baseline.** A polished demo alone is not proof.
3. **Failures are reported.** Missing data, a failed model call or an unverified assumption is stated in the output.
4. **Outputs outlive the chat.** Results are stored as versioned artifacts, not left in chat history.

---

## Status

These are working prototypes and proof-of-work projects, not certified products.
Prompterator is an MVP: data protection terms have not been legally reviewed, so do not enter personal or confidential data.
KYRON's public repository shows releases and verification evidence. The private implementation is not published.

Languages: German, English
