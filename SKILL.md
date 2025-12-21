---
name: source-of-truth
description: Create epistemically honest Source of Truth documents that pass Clarity Gate verification. Use when consolidating research, documenting project state, creating verification baselines, or building authoritative references. Triggers on "create source of truth", "document verified state", "consolidate research", "create verification baseline", "build authoritative reference".
---

# Source of Truth Creator v1.0

**Purpose:** Create Source of Truth documents that are epistemically calibrated and Clarity Gate-ready.

**Core Question:** "When someone reads this document, will they have accurate confidence in each claim?"

**Core Principle:** *"A Source of Truth that overstates certainty is worse than no Source of Truth -- it creates false confidence. Calibration matters more than completeness."*

**Prior Art:** This skill synthesizes established frameworks (GRADE, ICD 203, PRISMA, IIA Standards). Our contribution is practical accessibility, not new concepts. See [docs/PRIOR_ART.md](docs/PRIOR_ART.md).

**Origin:** Extracted from Clarity Gate meta-verification (2025-12-21). When we ran Clarity Gate on its own Source of Truth document, we discovered failure modes specific to SoT creation. See: [Clarity Gate SOURCE_OF_TRUTH.md](https://github.com/frmoretto/clarity-gate/blob/main/docs/research/SOURCE_OF_TRUTH.md)

---

## When to Use This Skill

**Use when:**
- Claims will be cited elsewhere
- Decisions depend on accuracy
- Document will be read by people who don't know your epistemic standards
- Creating authoritative reference for a project
- Consolidating research from multiple sources

**User phrases that trigger this skill:**
- "Create a source of truth for..."
- "Document the verified state of..."
- "I need an authoritative reference for..."
- "Consolidate this research into..."

**Do NOT use when:**
- Taking meeting notes (use simple markdown)
- Brainstorming (uncertainty is the point)
- Personal project logs (overkill)
- Quick summaries (no verification needed)
- Internal team scratchpads

For lightweight documentation, use plain markdown. This skill is for documents where epistemic rigor matters.

---

## The Recursion Problem

Source of Truth documents face a unique challenge:

1. A Source of Truth claims to be "VERIFIED"
2. But verification requires... a Source of Truth
3. At some point, claims bottom out in human judgment

**This skill doesn't solve the recursion -- it makes it visible.**

The goal is not infinite regress verification. The goal is:
- Clear marking of WHERE claims bottom out
- Honest confidence levels for each claim type
- Visual calibration so readers don't over-trust

---

## The Six Failure Modes

These patterns emerged from meta-verification of the Clarity Gate Source of Truth document. Modes 1-5 were discovered during that verification; Mode 6 was identified during review as a common pattern.

### 1. THE VERIFIED HEADER TRAP

**Problem:** Document header says "Status: VERIFIED" but body contains estimates, hypotheticals, and acknowledged uncertainties.

**Why it matters:** Readers skim headers. A "VERIFIED" badge creates false confidence in all contents.

| Fails | Passes |
|-------|--------|
| "Status: VERIFIED -- Ready for publication" | "Status: VERIFIED (with noted exceptions)" |
| "All claims verified as of [date]" | "External claims verified; internal claims marked by confidence level" |

**Fix:** Always qualify the header status, or use the Verification Summary box.

---

### 2. THE INTERNAL MEASUREMENT TRAP

**Problem:** Internal measurements (timing, counts, informal tests) marked as "Verified" with the same formatting as externally-validated claims.

**Why it matters:** "12 seconds" from one informal run is not equal to "12 seconds" from rigorous benchmarking.

| Fails | Passes |
|-------|--------|
| "Pipeline time: 12 seconds -- Verified: 2025-12-21" | "Pipeline time: ~12 seconds [single run, informal timing]" |
| "Manual review: 45 minutes -- Internal source" | "Manual review: ~45 minutes [ESTIMATED, not measured]" |

**Fix:** Add methodology notes: `[MEASURED: n=X, conditions Y]`, `[INFORMAL: single observation]`, `[ESTIMATED: author judgment]`

---

### 3. THE SELF-ASSESSMENT TRAP

**Problem:** Self-assigned scores (8.8/10, "High confidence") presented in tables that look like external validation.

**Why it matters:** Numeric scores trigger authority heuristics. "9.5/10" looks objective even when self-assigned.

| Fails | Passes |
|-------|--------|
| "Credibility: 9/10" in a metrics table | "**Self-Assessment:** Credibility: 9/10 (author judgment)" |
| "Confidence: High" | "Confidence: High (author assessment, not external audit)" |

**Fix:** Always label self-assessments explicitly in the table header or row.

---

### 4. THE ABSENCE-AS-PROOF TRAP

**Problem:** "No prior art found" marked as "Verified" when absence of evidence is not equal to evidence of absence.

**Why it matters:** A more thorough search might find what you missed. Gap claims are inherently uncertain.

| Fails | Passes |
|-------|--------|
| "Novel approach: Verified -- No prior art found" | "Novel approach: No prior art found (to author's knowledge, Dec 2025 search)" |
| "Gap exists: Verified" | "Gap exists (systematic search; absence harder to prove)" |

**Fix:** Add epistemological caveat to all "X doesn't exist" claims.

---

### 5. THE ILLUSTRATIVE-AS-DATA TRAP

**Problem:** Hypothetical examples (96% efficiency, 50-claim document) appear in data tables alongside measured values.

**Why it matters:** Examples become cited as data. "~96% reduction" migrates from illustrative to factual.

| Fails | Passes |
|-------|--------|
| "HITL efficiency: ~96% -- Verified: 2025-12-21" | "HITL efficiency: ~96% -- ILLUSTRATIVE EXAMPLE" |
| "48/50 claims pass automated checks" in metrics table | Move to examples section, not metrics |

**Fix:** Keep illustrative examples OUT of data tables. Use separate "Examples" sections.

---

### 6. THE STALENESS TRAP

**Problem:** "Verified: 2025-12-21" on rapidly-changing claims (competitor features, pricing, URLs).

**Why it matters:** A URL verified yesterday may 404 today. External claims have different shelf lives.

| Fails | Passes |
|-------|--------|
| "Competitor X has no RAG feature -- Verified: 2025-12-21" | "Competitor X has no RAG feature -- Verified: 2025-12-21 [CHECK BEFORE CITING]" |
| "Pricing: $99/month -- Verified: 2025-12-21" | "Pricing: $99/month -- Verified: 2025-12-21 [VOLATILE -- verify before use]" |

**Fix:** Add staleness markers:
- `[STABLE]` -- historical facts, standards, completed events
- `[CHECK BEFORE CITING]` -- competitor features, pricing, team info
- `[VOLATILE -- verify before use]` -- URLs, API endpoints, market data
- `[SNAPSHOT -- [date] only]` -- stock prices, user counts, rankings

---

## Staleness Risk Categories

| Category | Examples | Typical Shelf Life | Marker |
|----------|----------|-------------------|--------|
| **Stable** | Historical facts, published papers, standards | Years | [STABLE] |
| **Moderate** | Company descriptions, product categories | Months | [CHECK BEFORE CITING] |
| **Volatile** | Pricing, feature lists, API endpoints, URLs | Days to weeks | [VOLATILE] |
| **Snapshot** | Stock prices, user counts, rankings | Point-in-time only | [SNAPSHOT] |

---

## Minimum Viable Source of Truth

For simple projects, use this lightweight version (~40 lines when filled):

```markdown
# [Topic] -- Source of Truth

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

Use the **Full Template** below when you need:
- Gap analysis (claiming novelty)
- Self-assessment scores
- Prior art tracking
- Extensive source documentation
- Component status tracking

---

## Full Template

```markdown
# [Project/Topic] -- Source of Truth

**Last Updated:** [YYYY-MM-DD]  
**Owner:** [Name]  
**Status:** VERIFIED (see Verification Status below)  
**Version:** [X.Y]

---

## Verification Status

| Category | Status | Confidence | Staleness Risk |
|----------|--------|------------|----------------|
| External claims (stable) | Verified against sources | High | STABLE |
| External claims (volatile) | Verified [date] | High | CHECK BEFORE CITING |
| Internal claims | Verified by owner | High | Low |
| Measurements | [Formal/Informal] | [High/Medium] | Low |
| Gap claims | Systematic search | Medium | Medium |
| Estimates | Marked as such | N/A | N/A |
| Self-assessments | Author judgment | N/A | N/A |

**Last verified:** [date] by [owner]
**Exceptions:** [Specific caveats if any]
**Re-verify before use:** [List volatile claims]

---

## Verified Data

### External Sources -- Stable

| Claim | Value | Source | Reference | Verified | Staleness |
|-------|-------|--------|-----------|----------|-----------|
| [claim] | [value] | External | [URL/citation] | [date] | STABLE |

### External Sources -- Volatile

| Claim | Value | Source | Reference | Verified | Staleness |
|-------|-------|--------|-----------|----------|-----------|
| [claim] | [value] | External | [URL] | [date] | CHECK BEFORE CITING |

### Internal Sources

| Claim | Value | Methodology | Confidence | Verified |
|-------|-------|-------------|------------|----------|
| [claim] | [value] | [how measured] | [High/Medium/Low] | [date] |

---

## Estimates and Projections (NOT VERIFIED DATA)

| Claim | Value | Basis | Status |
|-------|-------|-------|--------|
| [claim] | ~[value] | [author estimate / calculation] | ESTIMATE |

---

## Status Tracker

| Component | Status | Notes |
|-----------|--------|-------|
| [component] | [None / Planned / In Progress / Completed] | [details] |

---

## Gap Analysis (Author Assessment)

| Domain | Existing Solutions | Gap Identified | Confidence |
|--------|-------------------|----------------|------------|
| [domain] | [what exists] | [what's missing] | [High/Medium] (search [date]) |

**Note:** Gap claims reflect author's search as of [date]. Absence of evidence is not equal to evidence of absence.

---

## Self-Assessment (Author Judgment)

**WARNING: These scores are self-assigned, not externally validated.**

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| [dimension] | [X/10] | [why] |

---

## Unverified Claims

Claims that appear elsewhere but require caution:

| Claim | Issue | Required Action | Status |
|-------|-------|-----------------|--------|
| [claim] | [why uncertain] | Mark as [ESTIMATED] / [ILLUSTRATIVE] | [Done/Pending] |

---

## Open Items

| ID | Priority | Description | Status | Owner |
|----|----------|-------------|--------|-------|
| 1 | [H/M/L] | [description] | [status] | [owner] |

---

## Changelog

### v[X.Y] ([YYYY-MM-DD])
- [change]

---

## Document Metadata

| Field | Value |
|-------|-------|
| Document Type | Source of Truth |
| Version | [X.Y] |
| Created | [YYYY-MM-DD] |
| Last Updated | [YYYY-MM-DD] |
| Owner | [Name] |
| Status | VERIFIED (with noted exceptions) |
```

---

## Quick Checklist

Run through before finalizing:

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

## Relationship to Clarity Gate

| This Skill | Clarity Gate |
|------------|--------------|
| Creates Source of Truth documents | Verifies any document |
| Prevents epistemic failures during creation | Detects epistemic failures after creation |
| Provides templates | Provides checklists |
| Focuses on calibration | Focuses on detection |

**Workflow:**
1. Use **Source of Truth Creator** to draft the document
2. Run **Clarity Gate** on the result
3. Iterate until PASS

---

## What This Skill Does NOT Do

- Does not verify external claims (use web search, citations)
- Does not replace domain expertise
- Does not guarantee completeness
- Does not solve the recursion problem (only makes it visible)

**This skill ensures:** Documents are structured for epistemic honesty, with appropriate uncertainty markers and reader calibration.

---

## Related

- **[Clarity Gate](https://github.com/frmoretto/clarity-gate)** -- Verification skill (use after creation)
- **[Stream Coding](https://github.com/frmoretto/stream-coding)** -- Full documentation-first methodology
- **[Prior Art](docs/PRIOR_ART.md)** -- Academic and industry sources
- **Author:** Francesco Marinoni Moretto

---

## Changelog

### v1.0 (2025-12-21)
- Initial release
- Six failure modes documented
- Full and minimum viable templates
- Staleness Risk Categories
- Quick checklist

---

**Version:** 1.0  
**Scope:** Source of Truth document creation  
**Output:** Epistemically calibrated Source of Truth document
