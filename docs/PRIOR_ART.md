# Source of Truth Creator — Prior Art

**Version:** 1.0  
**Last Updated:** 2025-12-21

---

## Overview

The Source of Truth Creator skill synthesizes proven frameworks from multiple domains into a lightweight, practitioner-focused tool. This document acknowledges the extensive prior art and identifies what's actually new.

**Key principle:** We're not claiming to invent epistemic calibration or integrated quality frameworks. Those exist and are more sophisticated than what we offer. Our contribution is **practical accessibility** — a simple checklist and template format for technical writers and founders who don't have time for 9-dimensional frameworks or automated pipelines.

---

## Honest Novelty Assessment

### Not Novel (Well-Established Prior Art)

| Component | Prior Art | Source | Maturity |
|-----------|-----------|--------|----------|
| Confidence levels | GRADE (4-level system) | Healthcare since 2000 | Global regulatory standard |
| Likelihood vs confidence | ICD 203 | Intelligence community | Mandatory for IC |
| Self-assessment vs external | IIA Audit Standards | Institute of Internal Auditors | Since 1990s |
| "Absence != evidence" principle | PRISMA, Cochrane | Systematic review methodology | Since 2003 |
| Data freshness/staleness tracking | DAMA-DMBOK, Chayka et al. 2012 | Data management | Mathematically formalized |
| Integrated quality frameworks | Treude 2020, Tsave 2025, OHAT 2014 | Multiple domains | 5-10 dimensions each |

### More Sophisticated Frameworks

Multiple integrated frameworks address similar or greater complexity:

| Framework | Dimensions | Scope | Our Assessment |
|-----------|------------|-------|----------------|
| Chayka et al. 2012 | Full measurement methodology | Data staleness | Solves Staleness Trap mathematically |
| Treude et al. 2020 | 10 dimensions | Software documentation | More sophisticated than our 6 modes |
| Tsave et al. 2025 | 5 dimensions + automation | Medical data quality | Completeness, validity, consistency, integrity, fairness |
| OHAT/Rooney 2014 | 7 steps + confidence rating | Systematic reviews | Industry standard for 10+ years |
| Clark et al. 2025 | 10 challenges | LLM epistemic alignment | Broader scope, similar goals |

### Our Actual Contribution

| Component | Status | Confidence |
|-----------|--------|------------|
| Six failure modes as unified framework | **Not novel** — similar integrations exist | High (verified) |
| Templates implementing all six | **Not novel** — medical frameworks have detailed templates | High (verified) |
| **Practitioner-focused simplicity** | Likely valuable | Medium |
| **Documentation-specific framing** | Narrow scope contribution | Medium |
| **Checklist format for non-specialists** | Accessibility contribution | Medium |

---

## Key Prior Art Frameworks

### Staleness Measurement Framework (Chayka et al. 2012)

**Citation:** Chayka, O., Palpanas, T., Bouquet, P. (2012). "Defining and Measuring Data-Driven Quality Dimension of Staleness." University of Trento, DISI Technical Report 12-016.

**What it does:** Provides a mathematical framework for measuring data staleness, including:
- Exponential smoothing for update frequency prediction
- Freshness vs staleness measurement methodology
- Aggregation approaches for data quality assessment

**Validation:** Tested on Wikipedia revision history data using exponential smoothing method.

**Relevance:** Staleness is arguably the most technically complex of our six failure modes. This framework provides the mathematical foundation — our "staleness markers" are a simplified practitioner version of this research.

---

### Software Documentation Quality Framework (Treude et al. 2020)

**Citation:** Treude, C., Middleton, J., Atapattu, T. (2020). "Beyond Accuracy: Assessing Software Documentation Quality." In *Proceedings of ESEC/FSE '20*, ACM.

**10 dimensions:**
1. Quality (spelling, grammar)
2. Appeal (engagement)
3. Readability
4. Understandability
5. Structure
6. Cohesion
7. Conciseness
8. Effectiveness
9. Consistency
10. Clarity

**Integration method:** Synthesizes Wang & Strong (1996), Eppler (16 dimensions), Knight & Burn (20 dimensions), and readability research.

**Validation:** Empirical testing with 4 technical editors across 41 documents in 5 genres.

**Relevance:** Demonstrates that integrating multiple quality dimensions is standard practice in documentation research. Their 10-dimension framework is more comprehensive than our 6 failure modes.

---

### Medical Data Quality Framework (Tsave et al. 2025)

**Citation:** Tsave, O., Kosvyra, A., Filos, D.T., Chouvarda, I. (2025). "A Multi-Dimensional Framework for Data Quality Assurance in Cancer Imaging Repositories." *Cancers*, 17(19):3213.

**5 dimensions:**
1. Completeness
2. Validity
3. Consistency
4. Integrity
5. Fairness

**Deployment:** Part of EU-funded INCISIVE project for pan-European cancer imaging repository.

**Relevance:** Demonstrates multi-dimensional data quality frameworks with automated validation — more technically sophisticated than our checklist approach.

---

### OHAT Systematic Review Framework (Rooney et al. 2014)

**Citation:** Rooney, A.A., Boyles, A.L., Wolfe, M.S., Bucher, J.R., Thayer, K.A. (2014). "Systematic Review and Evidence Integration for Literature-Based Environmental Health Science Assessments." *Environmental Health Perspectives*, 122(7):711-718.

**Confidence rating system:** Four levels (High, Moderate, Low, Very Low) with explicit downgrade/upgrade criteria.

**Adoption:** Adapted from GRADE methodology used by Cochrane Collaboration. Influenced EPA and other regulatory bodies' systematic review approaches.

**Relevance:** Our confidence marking concept is a simplified version of what OHAT formalized 11 years earlier.

---

## Sources for Individual Failure Modes

### GRADE Framework (Healthcare)

**What it is:** Grading of Recommendations, Assessment, Development, and Evaluation

**Four confidence levels:**
- HIGH — Very confident effect lies close to estimate
- MODERATE — Moderately confident; true effect likely close
- LOW — Limited confidence; true effect may be substantially different
- VERY LOW — Very little confidence in estimate

**What we learned:** The four-level system is well-validated. We adapted it for documentation context.

**Reference:** gdt.gradepro.org; BMJ, Cochrane Collaboration

---

### ICD 203 (Intelligence Community)

**What it is:** Intelligence Community Directive on Analytic Standards

**Key distinctions:**
- **Likelihood** — Probability of event occurring ("remote" to "nearly certain")
- **Confidence** — Analyst's confidence in the BASIS for judgment
- **Information** — Facts from sources
- **Assumptions** — Suppositions bridging gaps
- **Judgments** — Conclusions based on information + assumptions

**What we learned:** Separating likelihood from confidence prevents conflation. The Information/Assumptions/Judgments framework is powerful.

**Reference:** dni.gov/files/documents/ICD/ICD-203.pdf [STABLE]

---

### IIA Audit Standards (Self-Assessment)

**What it is:** Institute of Internal Auditors quality assurance standards

**Key requirement:** All self-assessments must be validated by independent external assessors at least once every five years.

**Empirical validation:** Self-assessment inflation is well-documented in audit literature:
- Karapetrovic & Willborn (2001) established the comparison framework between self-assessment and external audit (162 citations)
- Baker (2022) found statistically significant inflation in self-accreditation scores vs third-party audits (z = -6.4376, p < 0.05, n=73 SMBs)

**What we learned:** Self-assessment bias is empirically documented. Explicit labeling is essential.

**References:** 
- theiia.org (IIA Standards)
- Karapetrovic, S. & Willborn, W. (2001). "Audit and self-assessment in quality management." Emerald. (162 citations)
- Baker, B.F. (2022). "Self-Accreditations Versus Third-Party Audits: Understanding if Variances Exist When Assessing General Cybersecurity Frameworks." [Doctoral dissertation, California Southern University]. ProQuest.

---

### PRISMA/Cochrane (Absence Claims)

**What it is:** Standards for systematic review reporting

**Key findings:** 
- In 2001-2002, 21.3% of Cochrane review abstracts made unqualified "no effect" claims (Alderson & Chalmers 2003)
- By 2017, this dropped to 7.8% (Marson Smith et al. 2021)
- Shows the principle is well-known but implementation took 15+ years to improve significantly

**PRISMA 2020 requirement:** "Clearly indicate if studies were ineligible because outcomes were NOT measured."

**What we learned:** Absence claim hedging is established methodology but poorly implemented in practice. Templates that enforce marking may help adoption.

**References:**
- Alderson P, Chalmers I. "Survey of claims of no effect in Abstracts of Cochrane reviews." BMJ 2003;326:475-6.
- Marson Smith PR, Ware L, Adams C, Chalmers I. "Claims of 'no difference' or 'no effect' in Cochrane and other systematic reviews." BMJ Evidence-Based Medicine 2021;26:118-120.
- PRISMA 2020. BMJ 2021;372:n71

---

### Data Freshness (DAMA-DMBOK)

**What it is:** Data Management Body of Knowledge — data quality framework

**Key concepts:**
- Maximum data delay thresholds
- Freshness alerts and monitoring
- Update schedules and staleness tracking

**What we learned:** Freshness tracking is well-solved for data. We translated it to documentation (staleness markers).

**References:**
- DAMA-DMBOK 2.0
- Chayka et al. (2012) — mathematical formalization

---

## Mapping Prior Art to Our Six Failure Modes

| Failure Mode | Prior Art Exists? | Source | What We Add |
|--------------|-------------------|--------|-------------|
| 1. Verified Header Trap | Yes | Audit standards (qualified opinions), OHAT confidence | Practitioner wording |
| 2. Internal Measurement Trap | Yes | Scientific methodology (n, conditions), Treude 2020 | Template formalization |
| 3. Self-Assessment Trap | Yes | IIA Standards, Karapetrovic 2001, Baker 2022 | Documentation framing |
| 4. Absence-as-Proof Trap | Yes | PRISMA, Cochrane, OHAT | Enforcement template |
| 5. Illustrative-as-Data Trap | Partial | Visualization standards, Tsave 2025 | Explicit marking template |
| 6. Staleness Trap | **Mathematically formalized** | Chayka 2012, DAMA-DMBOK | Simplified markers |

---

## What We're NOT Claiming

1. **Not inventing integrated frameworks** — Treude (10 dimensions), Tsave (5 dimensions), OHAT (7 step framework) all predate us
2. **Not inventing confidence levels** — GRADE has done this for 20+ years
3. **Not inventing self-assessment warnings** — IIA Standards predate us by decades
4. **Not inventing absence claim hedging** — PRISMA/Cochrane established this
5. **Not inventing staleness measurement** — Chayka et al. mathematically formalized this in 2012
6. **Not claiming "first integrated framework"** — multiple exist with greater sophistication

## What We ARE Claiming

**Practical accessibility for documentation teams:**

1. A simple 6-item checklist (vs 9-10 dimension frameworks)
2. Copy-paste templates (vs academic methodologies)
3. Markdown format for technical writers
4. No automation required (vs production pipelines)
5. Readable in 10 minutes (vs journal papers)

**Our value proposition is simplicity, not sophistication.**

---

## Full Citation List

### Integrated Frameworks (Prior Art)
- Chayka, O., Palpanas, T., Bouquet, P. (2012). "Defining and Measuring Data-Driven Quality Dimension of Staleness." University of Trento.
- Treude, C., Middleton, J., Atapattu, T. (2020). "Beyond Accuracy: Assessing Software Documentation Quality." ESEC/FSE '20.
- Tsave, O. et al. (2025). "A Multi-Dimensional Framework for Data Quality Assurance in Cancer Imaging Repositories." Cancers.
- Rooney, A.A. et al. (2014). "Systematic Review and Evidence Integration." Environmental Health Perspectives.
- Clark, N. et al. (2025). "Epistemic Alignment: A Mediating Framework for User-LLM Knowledge Delivery." arXiv:2504.01205.

### Confidence & Calibration
- GRADE Working Group. gdt.gradepro.org
- ICD 203. dni.gov/files/documents/ICD/ICD-203.pdf

### Self-Assessment
- IIA Quality Assessment Manual. theiia.org
- Karapetrovic, S. & Willborn, W. (2001). "Audit and self-assessment in quality management." Emerald. (162 citations)
- Baker, B.F. (2022). "Self-Accreditations Versus Third-Party Audits." [Doctoral dissertation, California Southern University]. ProQuest. (z = -6.4376, p < 0.05, n=73)

### Absence Claims
- Alderson P, Chalmers I. (2003). "Survey of claims of no effect." BMJ;326:475-6.
- Marson Smith PR et al. (2021). "Claims of 'no difference' or 'no effect'." BMJ Evidence-Based Medicine;26:118-120.
- PRISMA 2020. BMJ 2021;372:n71

### Data Quality
- DAMA-DMBOK 2.0. dama.org

---

## Version History

| Version | Date | Changes |
|---------|------|--------|
| 1.0 | 2025-12-21 | Initial release. Citations verified against primary sources. |
