# Source of Truth Creator

**Create epistemically honest Source of Truth documents that pass verification.**

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

> *"A Source of Truth that overstates certainty is worse than no Source of Truth — it creates false confidence."*

---

## The Problem

You write a document labeled "Source of Truth" but it contains:
- Estimates formatted like verified data
- Self-assessments that look like external validation
- "No prior art found" stated as verified fact
- URLs verified yesterday that may 404 today

**The document looks authoritative. Readers trust it. But it overstates certainty.**

---

## What Is Source of Truth Creator?

A **practitioner-accessible** methodology and Claude skill for creating documents with **calibrated confidence** — where readers have accurate trust in each claim.

> **Novelty disclosure:** The six failure modes below synthesize established frameworks (GRADE, ICD 203, PRISMA, etc.). Our contribution is accessibility and documentation-specific implementation—not inventing new epistemic concepts. See [Prior Art & Transparency](#prior-art--transparency).

### The Six Failure Modes It Prevents

| Failure Mode | Problem | Solution |
|--------------|---------|----------|
| **Verified Header Trap** | Header says "VERIFIED" but body has estimates | Qualify: "VERIFIED (with noted exceptions)" |
| **Internal Measurement Trap** | Informal timing marked same as benchmarks | Add: `[single run, informal]` |
| **Self-Assessment Trap** | Self-scores look like external validation | Label: "Author judgment, not audited" |
| **Absence-as-Proof Trap** | "Not found" stated as verified | Add: "to author's knowledge, [date] search" |
| **Illustrative-as-Data Trap** | Examples appear in data tables | Separate: Examples section vs. Verified Data |
| **Staleness Trap** | No freshness warnings on volatile claims | Mark: `[STABLE]` / `[VOLATILE]` / `[CHECK BEFORE CITING]` |

---

### Prior Art & Transparency

This methodology synthesizes established frameworks from healthcare (GRADE), intelligence analysis (ICD 203), auditing (IIA Standards), and systematic reviews (PRISMA/Cochrane). Our innovation is practical accessibility and documentation-specific implementation—not inventing new epistemic concepts.

**Full prior art analysis available in [docs/PRIOR_ART.md](docs/PRIOR_ART.md)**, including:
- Comparison to existing frameworks (Treude, OHAT, Chayka, Tsave, Clark, and others)
- Honest assessment of what's novel vs. repackaged
- All citations verified against primary sources

---

## Quick Start

### Option 1: claude.ai / Claude Desktop

1. Download `SKILL.md` from this repo (or zip if available)
2. Go to Settings → Features → Skills → Add
3. Upload the file
4. Ask Claude: *"Create a source of truth for [topic]"*

### Option 2: Claude Code

1. Copy `SKILL.md` to your project's skills folder
2. Claude Code will automatically detect and use it
3. Ask Claude: *"Create a source of truth for [topic]"*

### Option 3: Claude Projects

Add `SKILL.md` to project knowledge. Claude will search it when needed, though Skills provide better integration.

### Option 4: Manual / Other LLMs

For other AI tools or manual use, check documents for these patterns:

| Pattern | Action |
|---------|--------|
| Header says "VERIFIED" but body has estimates | Qualify: "VERIFIED (with noted exceptions)" |
| Informal timing ("took about 2 hours") | Add: `[single run, informal]` |
| Self-scores without external validation | Label: "Author judgment, not audited" |
| "No X exists" / "Not found" | Hedge: "to author's knowledge, [date] search" |
| Examples mixed in data tables | Move to separate "Examples" section |
| URLs, pricing, feature lists | Mark: `[VOLATILE]` or `[CHECK BEFORE CITING]` |

**For Cursor/Windsurf:** Extract the 6 failure modes and templates into your `.cursorrules`. The methodology is tool-agnostic—only SKILL.md is Claude-optimized.

---

## How This Compares to Related Frameworks

| Framework | Scope | Best For | Trade-off |
|-----------|-------|----------|----------|
| Treude et al. (2020) | 10 dimensions | Comprehensive documentation audits | More thorough; we're a simplified subset |
| OHAT/Rooney (2014) | 7 steps + confidence | Systematic reviews | Industry standard; use if high-assurance needed |
| Chayka et al. (2012) | Mathematical staleness | Data quality measurement | Use for high-stakes; our approach is practitioner-friendly |

**When to use Source of Truth Creator:** You need structured confidence calibration but lack time for 10-dimensional frameworks.

---

## When to Use This

**Use when:**
- Claims will be cited elsewhere
- Decisions depend on accuracy
- Readers don't know your epistemic standards
- Creating authoritative project reference
- Consolidating research from multiple sources

**Don't use when:**
- Taking meeting notes (use simple markdown)
- Brainstorming (uncertainty is the point)
- Personal project logs (overkill)
- Quick summaries (no verification needed)

---

## Minimum Viable Template

For simple projects (~40 lines when filled):

```markdown
# [Topic] — Source of Truth

**Last Updated:** [YYYY-MM-DD]  
**Owner:** [Name]  
**Status:** VERIFIED (with noted exceptions)

---

## Verification Status

| Category | Status | Confidence |
|----------|--------|------------|
| External claims | Verified | High |
| Internal claims | Owner verified | High |
| Measurements | [Formal/Informal] | [High/Medium] |
| Estimates | Marked as such | N/A |

**Exceptions:** [Any caveats]

---

## Verified Data

| Claim | Value | Source | Verified | Staleness |
|-------|-------|--------|----------|-----------|
| [claim] | [value] | [source] | [date] | [STABLE/VOLATILE] |

---

## Estimates (NOT VERIFIED)

| Claim | Value | Basis |
|-------|-------|-------|
| [claim] | ~[value] | [author estimate] |

---

## Open Items

| Priority | Description | Status |
|----------|-------------|--------|
| [H/M/L] | [description] | [status] |
```

*Template format adapted from medical/audit documentation standards. See [docs/PRIOR_ART.md](docs/PRIOR_ART.md) for sources.*

See [SKILL.md](SKILL.md#full-template) for the comprehensive template with gap analysis, self-assessment sections, and changelog.

---

## Quick Checklist

Before finalizing any Source of Truth document:

| Check | Pass? |
|-------|-------|
| Header status qualified ("with noted exceptions")? | |
| Verification Status box present? | |
| Internal measurements marked with methodology? | |
| Self-assessments labeled as author judgment? | |
| "X doesn't exist" claims hedged? | |
| Illustrative examples NOT in data tables? | |
| Estimates in separate section from verified data? | |
| Volatile claims marked with staleness warnings? | |
| "Re-verify before use" list for URLs/competitors? | |

---

## Staleness Risk Categories

| Category | Examples | Shelf Life | Marker |
|----------|----------|------------|--------|
| **Stable** | Historical facts, published papers, standards | Years | `[STABLE]` |
| **Moderate** | Company descriptions, product categories | Months | `[CHECK BEFORE CITING]` |
| **Volatile** | Pricing, feature lists, API endpoints, URLs | Days to weeks | `[VOLATILE]` |
| **Snapshot** | Stock prices, user counts, rankings | Point-in-time only | `[SNAPSHOT]` |

---

## The Recursion Problem

Source of Truth documents face a unique challenge:

1. A Source of Truth claims to be "VERIFIED"
2. But verification requires... a Source of Truth
3. At some point, claims bottom out in human judgment

**This skill doesn't solve the recursion — it makes it visible.**

The goal is:
- Clear marking of WHERE claims bottom out
- Honest confidence levels for each claim type
- Visual calibration so readers don't over-trust

---

## Relationship to Clarity Gate

| Source of Truth Creator | Clarity Gate |
|------------------------|--------------|
| **Creates** documents | **Verifies** documents |
| Prevents failures during creation | Detects failures after creation |
| Provides templates | Provides checklists |
| Focuses on calibration | Focuses on detection |

**Recommended workflow:**
1. Use **Source of Truth Creator** to draft the document
2. Run **[Clarity Gate](https://github.com/frmoretto/clarity-gate)** on the result
3. Iterate until PASS

---

## Prior Art

See [Prior Art & Transparency](#prior-art--transparency) above and [docs/PRIOR_ART.md](docs/PRIOR_ART.md) for full analysis, citations, and honest novelty assessment.

---

## Examples

| Example | Description |
|---------|-------------|
| [Clarity Gate Research](https://github.com/frmoretto/clarity-gate/blob/main/docs/research/SOURCE_OF_TRUTH.md) | Meta-example: research documentation for a sister project |

See [examples/README.md](examples/README.md) for more.

---

## Documentation

| Document | Description |
|----------|-------------|
| [SKILL.md](SKILL.md) | Claude skill with full templates and failure modes |
| [docs/PRIOR_ART.md](docs/PRIOR_ART.md) | Academic and industry sources |
| [examples/](examples/) | Real-world Source of Truth documents |

---

## Related

**Clarity Gate** — Verification skill (use after creation)  
[github.com/frmoretto/clarity-gate](https://github.com/frmoretto/clarity-gate)

**Stream Coding** — Documentation-first methodology where these tools originated  
[github.com/frmoretto/stream-coding](https://github.com/frmoretto/stream-coding)

---

## License

CC BY 4.0 — Use freely with attribution.

---

## Author

**Francesco Marinoni Moretto**
- GitHub: [@frmoretto](https://github.com/frmoretto)
- LinkedIn: [francesco-moretto](https://www.linkedin.com/in/francesco-moretto/)

---

## Contributing

Looking for:

1. **Failure modes** — Did we miss common patterns?
2. **Templates** — Domain-specific variations (legal, medical, technical)?
3. **Prior art** — Sources we should acknowledge?
4. **Real examples** — Source of Truth documents to learn from?

Open an issue or PR.
