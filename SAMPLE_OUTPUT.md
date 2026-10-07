# Sample Output — T2 Framework / Model / Method

> **Synthetic example.** The source, author, framework, figures, and anchors below are fictional and exist only to demonstrate formatting. This sample demonstrates **T2**, not the universal structure for every document.

```yaml
---
title: "The Constraint Loop"
author: "Mira Chen"
source_file: "the-constraint-loop-synthetic.md"
source_edition: "1st edition"
publication_date: "2026"
categories:
  - Strategy
  - Operations
concepts:
  - bottleneck
  - throughput
  - constraint discovery
  - feedback loop
level: "Intermediate"
primary_template: "T2"
coverage:
  status: "full"
  note: "Synthetic source inspected in full: sections 1–5 and Appendix A."
---
```

# The Constraint Loop

**Use when:** a system's output is below target, local teams appear busy but total throughput is stagnant, or improvement initiatives keep moving the bottleneck instead of removing it.

## CORE THESIS

**Author's Argument.** Chen argues that system performance is usually limited by a small number of active constraints rather than by the average efficiency of every component. Optimizing non-constrained components can increase local utilization without improving total throughput. The proposed method therefore begins with identifying the active constraint, concentrating improvement effort there, and then re-observing the system because the binding constraint may move after an intervention. [S1: §1 "Why Local Efficiency Misleads"; §2 "The Active Constraint"]

## PRIMARY FRAMEWORK / MODEL

### Constraint Loop

**Source-Reported.**

**Purpose / problem:** identify the current limiting factor in a flow system and focus intervention where it can change total system output. [S1: §2]

**Native structure:** iterative loop.

**Components / steps:**

1. **Observe total flow** — establish the output measure the system is meant to improve.
2. **Locate the active constraint** — identify the stage whose effective capacity or operating condition limits total flow.
3. **Exploit before expanding** — remove avoidable loss around the constraint before adding resources.
4. **Subordinate local optimization** — avoid upstream or downstream behavior that increases work without increasing total flow.
5. **Re-measure** — after intervention, observe whether throughput improved and whether the binding constraint moved. [S1: §3 "The Five Moves"]

**Inputs:** the source calls for system-level throughput data and observations of queue accumulation around process stages. [S1: §2.2]

**Outputs:** identification of the current constraint and a prioritized intervention target. [S1: §3]

**How to use / read it:** repeat the loop after each material intervention rather than assuming the original constraint remains binding. [S1: §3.5]

**Rules / thresholds:** no numeric threshold for declaring a constraint is provided in the synthetic source. [S1: §2.3]

**Assumptions:** the system has an observable flow objective and stages whose interactions materially affect total output. [S1: §1.3]

**Scope boundaries:** the method is written for repeatable operating flows; the author does not claim that it maps directly to one-off creative work. [S1: §4.2]

**Reported failure modes:** the source warns that teams may mistake the longest queue for the causal constraint when batching rules or scheduled downtime are responsible for the queue. [S1: §4.1]

## SUPPORTING PRINCIPLES

### Local efficiency is not system performance

**Author's Argument.** Increasing utilization at a non-constrained stage can create more work-in-process without increasing completed output. The relevant measure is improvement at system level, not whether every resource remains busy. [S1: §1.2]

### The constraint can move

**Source-Reported.** The framework treats constraint identification as temporary rather than permanent. A successful intervention may shift the limiting factor to another stage, which is why re-measurement is part of the loop. [S1: §3.5]

### Capacity expansion is not the first move

**Author's Heuristic.** Chen recommends first removing avoidable loss around the constraint before purchasing additional capacity. The source presents this as an operating heuristic and does not report a controlled test proving that it is optimal in all settings. [S1: §3.3; Appendix A]

## IMPLEMENTATION / CHECKLIST

**Curator Inference — Derived Structure.** The following checklist reorganizes the five moves and the source's warnings into a compact usage aid; it is not presented as a checklist by the fictional author.

- [ ] Define the system-level output being improved. [Premise: S1 §1.3]
- [ ] Identify the stage currently limiting that output. [Premise: S1 §2]
- [ ] Check whether the apparent bottleneck is caused by batching, downtime, or another operating rule. [Premise: S1 §4.1]
- [ ] Remove avoidable loss at the constraint before adding capacity. [Premise: S1 §3.3]
- [ ] Avoid local optimization that increases work-in-process without improving completed output. [Premise: S1 §3.4]
- [ ] Re-measure the system after intervention. [Premise: S1 §3.5]

**Limitation of the inference:** this checklist preserves the synthetic source's elements but imposes checklist formatting for retrieval convenience. It does not add decision thresholds or guarantee that following the sequence will improve every system.

## EVIDENCE PROFILE AND LIMITATIONS

**Source-Reported.** The synthetic source supports the framework with three operating case narratives and before/after throughput figures. It does not report randomization, a matched comparison group, or confidence intervals. [S1: Appendix A]

The cases cover a distribution center, a packaging line, and a service queue over observation windows ranging from six to eleven weeks. The source explicitly cautions that the cases illustrate the method rather than establish a universal causal effect. [S1: Appendix A.1–A.3]

**Curator Inference.** The inspected material therefore supports treating the Constraint Loop as a diagnostic and prioritization framework demonstrated in several synthetic operating examples, but not as a universally validated law of system performance. This inference is based on the reported case design and the source's own limitation statement. [Premise: S1 Appendix A; §4.3]

## RELATED MATERIAL

Not mapped.

## SOURCES AND COVERAGE

**S1** = `the-constraint-loop-synthetic.md`, fictional 1st edition, 2026. Sections 1–5 and Appendix A inspected in full. All anchors in this sample refer to headings inside the synthetic source; no external material was used.

**Template:** T2 — Framework / Model / Method  
**Recommended filename:** `Strategy_TheConstraintLoop_Summary_v1.md`
