# AI-Assisted Product Operating System

**A vendor-neutral methodology for transforming ambiguous business problems into engineering-ready product recommendations and executive-ready communication through AI-assisted workflows, explicit human governance, and accountable Product Ownership.**

> AI does not replace Product Ownership. It accelerates it.

## Why this exists

AI is increasingly used in product work, but often in an ad hoc way. The AI-Assisted Product Operating System (AAPOS) provides a repeatable operating model for using AI across discovery, prioritization, engineering planning, and executive communication while keeping human judgment as the control layer.

This is not a prompt library. The prompts and skills in this repository are reference implementations of a broader methodology.

## Who This Is For

This operating system is for:

- Product Owners and Product Managers turning ambiguous requests into clear product direction
- Product Operations teams standardizing intake, prioritization, governance, and handoff
- AI workflow owners who need human review gates and accountable decision records
- Delivery teams that need product intent clarified before engineering planning begins
- Leaders who need executive-ready communication without losing the product reasoning behind it

## Start Here

Read these first:

1. [`docs/operating-model.md`](docs/operating-model.md) for the full stage-by-stage workflow.
2. [`docs/human-governance.md`](docs/human-governance.md) for review gates, approval expectations, and accountability boundaries.
3. [`docs/vued-risk-framework.md`](docs/vued-risk-framework.md) for the Value, Urgency, Effort, Dependencies, and Risk decision model.

Then review [`docs/artifact-model.md`](docs/artifact-model.md) to understand how outputs move from discovery to recommendation, engineering planning, and executive communication.

## Operating model

```text
Business Problem
      |
      v
Product Discovery
      |
      v
Human Review Gate
      |
      v
Product Recommendation
      |
      v
Human Approval Gate
      |
      v
Engineering Planning
      |
      v
Human + Engineering Review Gate
      |
      v
Executive Communication
      |
      v
Human Final Approval
```

## The four stages

| Stage | Purpose | Reference implementation | Primary artifact |
|---|---|---|---|
| 1. Product Discovery | Turn ambiguity into a structured understanding of the problem | Claude: `/vued clarifying questions` | Discovery Summary |
| 2. Product Recommendation | Apply VUED + Risk and produce an approved Product plan | Claude: `/vued product plan` | Approved Product Recommendation |
| 3. Engineering Planning | Translate locked Product strategy into engineering-ready planning | Codex: `engineering-refinement-planner` | Engineering Refinement Package + Workbook |
| 4. Executive Communication | Translate Product and Engineering work into a business-audience decision artifact | Claude: `engineering-readiness-review` | Engineering Readiness Review |

## Sanitized Example

A team receives an ambiguous request to add AI-assisted decision support to an internal workflow.

The operating system would guide the Product Owner through:

1. Clarifying the business problem, users, constraints, risks, and unknowns.
2. Applying VUED + Risk to separate urgency from actual product value.
3. Defining the smallest governed MVP that can be reviewed and validated.
4. Locking product intent before engineering planning begins.
5. Translating the approved direction into engineering-ready refinement artifacts.
6. Preparing executive communication that explains the decision, tradeoffs, open assumptions, and governance controls.

The output is not an automatic decision. It is a reviewable product decision package with human approval gates.

## Core principles

- **Human judgment is the control layer.**
- **Discovery before commitment.**
- **AI assists; humans decide and remain accountable.**
- **Product intent is locked before Engineering planning begins.**
- **Product drives Engineering; Engineering does not redefine Product.**
- **Translate, do not transcribe.**
- **Every artifact serves one audience.**
- **Make uncertainty and dependencies visible.**
- **Separate mitigation, discovery, MVP, and full solution.**
- **Avoid false precision.**

## Decision framework: VUED + Risk

AAPOS evaluates work through five lenses:

- **Value**: user impact, revenue, retention, operational efficiency, strategic alignment, and scale.
- **Urgency**: deadlines, production impact, escalation, cost of delay, and whether the problem is worsening.
- **Effort**: delivery complexity and unknowns, without inventing estimates.
- **Dependencies**: systems, teams, controls, vendors, sequencing constraints, and approvals.
- **Risk**: a mandatory overlay covering both the risk of acting and the risk of not acting.

Risk remains separate because high-value, urgent work can still be unsafe, and low-effort work can still create unacceptable exposure.

## Human governance

No AI-generated output automatically becomes a decision, requirement, backlog item, or stakeholder communication.

At each stage, the Product Owner reviews, edits, accepts, or rejects the output. The Product Owner remains responsible for:

- discovery quality
- product judgment
- prioritization
- scope
- tradeoffs
- stakeholder alignment
- engineering readiness
- final communication
- accountability for the outcome

Recommended artifact metadata:

```text
Drafted with AI assistance
Human reviewed: Yes / No
Approved by:
Approval date:
Open assumptions:
```

## Repository map

- [`docs/operating-model.md`](docs/operating-model.md)
- [`docs/human-governance.md`](docs/human-governance.md)
- [`docs/vued-risk-framework.md`](docs/vued-risk-framework.md)
- [`docs/artifact-model.md`](docs/artifact-model.md)
- [`skills/claude/vued-product-prioritization.md`](skills/claude/vued-product-prioritization.md)
- [`skills/claude/engineering-readiness-review.md`](skills/claude/engineering-readiness-review.md)
- [`skills/codex/engineering-refinement-planner.md`](skills/codex/engineering-refinement-planner.md)

## What this repository is not

AAPOS is not tied to one company, interview, product domain, model, or vendor. Claude and Codex are current reference implementations. The operating system remains usable if those tools change.

## Status

**Version 1.0 architecture is frozen.** Current work is focused on documentation, reference implementations, and examples.
