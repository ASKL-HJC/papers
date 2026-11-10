# AGENTS.md — IEEE Journal Paper Writing

## Scope

This project uses Codex/AI agents to assist with IEEE journal manuscript writing.

Primary domains include:
- robotics
- UAVs
- autonomous systems
- control
- planning
- estimation
- SLAM
- reinforcement learning for control
- embedded/autonomous systems

Default target style:
IEEE Transactions / Journals / Letters.

Target-journal instructions always override generic rules in this file.

---

## Core Principle

Write from evidence, not from desired conclusions.

The manuscript should follow:

evidence → claim → argument → prose

Never reverse this into:

desired prose → invented support

Every important technical claim must be traceable to:
- experimental data
- figures or tables
- mathematical analysis
- implementation evidence
- verified literature
- author-provided facts

Never invent:
- numerical results
- experiments
- baselines
- citations
- mechanisms
- parameter values
- implementation details
- novelty
- conclusions

If evidence is missing, report the evidence gap explicitly.

---

## Skill Priority Table

| Task | Preferred Skill |
|---|---|
| Section drafting / restructuring | `nature-writing` |
| Claim–evidence alignment | `nature-writing` |
| English polishing | `nature-polishing` |
| Chinese → academic English | `nature-polishing` |
| Literature discovery | literature/research skill |
| Citation verification | citation skill |
| Experimental sufficiency | IEEE experiment/reviewer skill |
| Reviewer-style audit | reviewer skill |
| IEEEtran / LaTeX | IEEE/LaTeX skill |
| Figures and tables | figure/table skill |
| Numerical/statistical analysis | direct computation/tool |

Do not load multiple large writing skills when one is sufficient.

---

## Role of `nature-writing`

Use `nature-writing` as the primary scientific-writing and argument-structuring skill.

Its main value is:
- claim–evidence alignment
- section-aware drafting
- evidence hierarchy
- argument restructuring
- claim-strength calibration
- removal of redundant prose

Do not blindly imitate Nature editorial style.

For IEEE manuscripts:
preserve its reasoning framework,
but prefer explicit engineering structure,
technical completeness,
quantitative evidence,
and reproducibility.

---

## General IEEE Writing Style

Prefer:
- precise technical language
- explicit objects and conditions
- defined terminology
- restrained claims
- quantitative comparisons
- clear method boundaries
- reproducible details

Avoid:
- vague significance claims
- dramatic discovery language
- unsupported superlatives
- excessive rhetorical language
- generic AI-style filler
- unexplained claims such as "significantly improved"

When possible, replace qualitative claims with measurable evidence.

---

## Abstract

Use `nature-writing` when drafting or restructuring the Abstract.

Preferred IEEE logic:

problem  
→ technical gap  
→ proposed method  
→ key mechanism  
→ evaluation setting  
→ quantitative result  
→ bounded conclusion

Write the final Abstract after the main Results section is stable.

The Abstract should:
- be self-contained
- emphasize concrete results
- avoid unsupported impact claims
- avoid literature review
- avoid unnecessary background

Do not introduce results not shown in the manuscript.

---

## Introduction

Use `nature-writing` for Introduction drafting and restructuring.

Preferred logic:

1. problem context
2. technical difficulty
3. representative existing approaches
4. limitations of those approaches
5. unresolved research gap
6. proposed method
7. contributions

Do not turn the Introduction into a chronological literature list.

Literature should support the research gap.

For IEEE engineering papers, explicit contribution statements are allowed and often preferred.

Typical contribution structure:

- proposed method/system
- technical mechanism or formulation
- experimental validation
- practical or theoretical advantage

Each contribution must later be supported by evidence.

---

## Related Work

Use `nature-writing` only for organization and narrative restructuring.

Do not use it as the authority for literature discovery.

Organize papers by:
- technical problem
- methodology
- assumptions
- system architecture
- limitations
- application scenario

Prefer comparison over paper-by-paper summaries.

The section should explain why the current method is needed.

Do not criticize prior work more strongly than the cited evidence supports.

---

## Problem Formulation

Prioritize technical correctness over writing elegance.

Clearly define:
- system
- variables
- symbols
- coordinate frames
- assumptions
- inputs
- outputs
- constraints
- optimization/control objectives

Do not compress definitions merely to improve prose flow.

All symbols should be defined before or immediately after first use.

---

## Methodology

Use `nature-writing` when:
- method logic is unclear
- section order is weak
- module relationships are confusing
- rationale is missing
- implementation notes need conversion into manuscript prose

Preferred structure:

problem formulation  
→ system/model  
→ architecture  
→ module design  
→ mathematical derivation  
→ algorithm  
→ implementation

Technical completeness has priority over stylistic compression.

Preserve:
- equations
- assumptions
- parameter definitions
- algorithmic conditions
- interface relationships
- implementation constraints
- reproducibility-critical details

Do not hide weak method logic behind polished prose.

---

## Experiments

Use `nature-writing` strongly for Results and experiment organization.

Before drafting, build a claim–evidence map.

Typical experiment categories:
- main comparison
- baseline comparison
- ablation
- robustness
- sensitivity
- generalization
- computational cost
- latency
- real-time performance
- deployment tests
- failure cases

Organize experiments around research questions or claims,
not merely in chronological order.

Every major claim from the Abstract and Introduction should have identifiable evidence.

---

## Results

A Results paragraph should normally contain:

observation  
→ quantitative evidence  
→ comparison  
→ interpretation

Keep observation and interpretation distinguishable.

Prefer:
- exact values
- relative improvement
- confidence intervals where applicable
- clearly defined metrics
- explicit operating conditions

Do not write:
"the proposed method performs significantly better"

unless statistical significance was actually tested.

Use more precise wording when appropriate:
"reduced RMSE by 18.4%"
or
"achieved lower RMSE in all tested scenarios."

---

## Discussion

Use `nature-writing` when interpretation is needed.

Preferred reasoning:

observation  
→ interpretation  
→ possible mechanism  
→ limitation  
→ implication

Do not present a plausible explanation as a proven mechanism.

Separate:
- demonstrated facts
- reasonable interpretations
- hypotheses

Keep engineering Discussion technically grounded.

If the target journal does not require a separate Discussion section,
integrate necessary interpretation into Results or Conclusion.

---

## Conclusion

Use `nature-writing` for compression and claim calibration.

Summarize:
- problem
- proposed method
- strongest result
- technical significance
- limitations/future work if appropriate

Do not:
- repeat the Abstract verbatim
- introduce new results
- introduce new claims
- exaggerate generality

---

## Language Polishing

Use `nature-polishing` after technical content is stable.

Do not polish unstable technical sections repeatedly.

Polishing must preserve:
- numerical values
- symbols
- equations
- causal strength
- uncertainty
- technical meaning

A more fluent sentence is not acceptable if it strengthens the original claim.

---

## Evidence Boundaries

When evidence is insufficient, use internal labels such as:

[EVIDENCE NEEDED]  
[CITATION NEEDED]  
[RESULT NEEDED]  
[VERIFY CLAIM]  
[AUTHOR CONFIRMATION REQUIRED]

Do not silently fill these gaps.

If a claim depends on an unavailable experiment,
recommend the experiment instead of inventing the result.

---

## Citations

Never fabricate references.

A citation must be verified before being treated as authoritative.

Separate:
- literature discovery
- citation verification
- manuscript drafting

Do not assume a cited paper supports a claim solely from its title or abstract.

Prefer primary sources.

---

## Figures and Tables

Figures and tables are evidence, not decoration.

Each figure/table should support a specific manuscript claim.

Check:
- readable labels
- defined units
- consistent symbols
- meaningful captions
- clear baselines
- valid statistical presentation
- legibility in IEEE column width

Avoid repeating every table value in prose.

Describe the finding, not the table structure.

---

## IEEE Formatting

Use dedicated IEEE/LaTeX skills for:
- IEEEtran
- references
- equation formatting
- figure placement
- table formatting
- section numbering
- bibliography
- page layout

Do not ask `nature-writing` to solve formatting problems.

---

## Reviewer Audit

Before finalizing a manuscript, inspect it as a reviewer.

Check:
- Is the research gap explicit?
- Is the novelty concrete?
- Are contributions supported?
- Are baselines fair?
- Are experimental conditions clear?
- Are ablations sufficient?
- Are robustness claims tested?
- Are real-time claims measured?
- Are limitations acknowledged?
- Can major results be reproduced?
- Are citations appropriate?
- Are claims stronger than evidence?

Prefer identifying a weakness over masking it with prose.

---

## Recommended Workflow

For a new manuscript:

collect materials  
→ verify evidence  
→ define target journal  
→ establish claims  
→ map claims to evidence  
→ build outline  
→ draft Introduction  
→ draft Methodology  
→ draft Experiments/Results  
→ draft Discussion  
→ draft Conclusion  
→ draft Abstract  
→ verify citations  
→ reviewer audit  
→ language polishing  
→ IEEE formatting  
→ final consistency check

---

## Final Rule

When choosing between:

better prose

and

more accurate technical meaning,

always preserve technical meaning.

The goal is not to make the manuscript sound impressive.

The goal is to make the technical contribution clear,
supported,
reproducible,
and defensible under peer review.