# Stage Manager — Artful Making Skill Library

> **How you move through your work is what you build.**

A free, open collection of 13 skills for vibe coders who want to stay the author while building with AI tools.

These skills help you expand options before converging, maintain coherence across a build, and keep the soul of the work intact while Claude Code, Cursor, Replit, or any agentic coding tool runs at speed.

This branch (`enhanced-cli-skills`) also includes **enhanced Compound Engineering workflows** — the full CE pipeline with Stage Manager gates woven into every phase.

---

## Quick Install

Already have [Compound Engineering](https://github.com/anthropics/courses/tree/master/compound_engineering) installed? One command:

```bash
git clone -b enhanced-cli-skills https://github.com/Mnfst-AI/Stage_Manager_Skills.git
cd Stage_Manager_Skills
bash install-enhanced-ce.sh
```

Or install directly:

```bash
curl -fsSL https://raw.githubusercontent.com/Mnfst-AI/Stage_Manager_Skills/enhanced-cli-skills/install-enhanced-ce.sh | bash
```

The installer will:
- Back up your original CE commands to `~/.claude/commands/ce.backup/`
- Install enhanced CE commands with Stage Manager gates
- Symlink all 13 Stage Manager skills to `~/.claude/skills/`
- Link shared reference files

To roll back: `cp ~/.claude/commands/ce.backup/* ~/.claude/commands/ce/`

---

## What These Skills Are

Each skill is a plain-text file — a recipe that tells an AI coach how to help you with a specific moment in your flow cycle. No magic. No proprietary platform required.

Drop them into your system prompt. Reference them in your IDE. Use them with any AI tool that accepts context.

They work best in sequence — but any one of them works on its own.

---

## The Flow Cycle

Stage Manager organizes the builder's work into three nodes:

**Shape** — exploring the problem space before converging on a solution
**Stage** — building in small, intentional increments with full agency
**All Nodes** — coherence checks that run at any transition point

The skills support every phase — and the transitions between them.

---

## The 13 Skills

### Shape Node

| Skill | Slash Command | What It Does |
|---|---|---|
| **Find the Holes** | `/shape-find-holes` | Maps every place in a spec where a coding tool will invent behavior you didn't ask for. P1/P2/P3 priority scoring. Interactive hole resolution. |
| **Collapsed Options** | `/shape-collapsed-options` | Finds decisions you already made without knowing it — especially where you're trying to do something different. P1/P2/P3 priority scoring. |
| **Risk Sequence** | `/shape-risk-sequence` | Surfaces load-bearing assumptions and sequences by cost-if-wrong. P1/P2/P3 priority scoring. Shows what to prove first. |
| **Soul Check** | `/shape-soul-check` | Deep 10-15 minute read on whether the original animating idea is still alive in the artifact. For quick checks, use Coherence Check. |

### Shape → Stage Transition

| Skill | Slash Command | What It Does |
|---|---|---|
| **Shape-to-Stage Gate** | `/sense-shape-to-stage-gate` | Five readiness questions before staging begins. Prevents premature staging and over-shaping. Verdicts: Ready, Almost, Not Yet. |

### Stage Node

| Skill | Slash Command | What It Does |
|---|---|---|
| **Chunking** | `/stage-chunking` | Breaks work into flow-cycle-sized pieces — each promptable, testable, and sequenced by cost of delay. |
| **Cost of Delay** | `/stage-wsjf` | Sequences stories by what it costs to wait — economic, risk, flow, and joy costs. H/M/L scoring. |
| **Prompt Craft** | `/stage-prompt-craft` | Turns a shaped chunk into a scoped, guardrailed prompt. Six parts: context, goal, scope, constraints, DoD, guardrails. P1/P2/P3 invention scoring. |
| **Prompt Guard** | `/stage-prompt-guard` | Reviews a crafted prompt before sending — flags every invisible decision the prompt itself is making. |
| **Live Mirror** | `/stage-live-mirror` | Compares plan vs. code output after a coding session. Surfaces every invisible decision the tool made. |
| **Output Review** | `/stage-output-review` | Three-layer review: definition of done, original intent, what it sets up next. Verdicts: Accept, Revise, Return. |
| **Decision Capture** | `/stage-decision-capture` | Full decisions-made manifest after a build — every choice the tool made that wasn't in the spec. |

### All Nodes

| Skill | Slash Command | What It Does |
|---|---|---|
| **Coherence Check** | `/coherence-check` | Lightweight 2-minute gate at any transition point. For deep artifact reads, use Soul Check. |

---

## Enhanced Compound Engineering

The `enhanced-cli-skills` branch includes modified CE workflows that integrate Stage Manager at every phase:

| CE Command | Stage Manager Integration |
|---|---|
| `/ce:brainstorm` | Coherence Check at close — confirms the brainstorm output is still aligned before planning |
| `/ce:plan` | Find the Holes + Risk Sequence gates — surfaces spec gaps and load-bearing assumptions before work begins |
| `/ce:work` | Prompt Guard before coding, Live Mirror after each session — flags invisible decisions in real time |
| `/ce:review` | Output Review + Decision Capture — three-layer review plus full manifest of tool-made choices |
| `/ce:compound` | Soul Check — ensures the documented learning still reflects the original intent |

Original CE commands are preserved at `/ce.backup:*` and work exactly as before.

---

## How to Read the Suite

**Risk Sequence** retires load-bearing assumptions before building. Once assumptions are confirmed, **Cost of Delay** sequences the confirmed work.

**Find the Holes** maps gaps the AI will invent into. **Collapsed Options** maps decisions the builder already made without knowing it. Run both before staging.

**Soul Check** is a deep read on a single artifact — 10-15 minutes. **Coherence Check** is the lightweight transition gate — 2 minutes, any artifact, any moment of doubt.

**Shape-to-Stage Gate** runs once, at the boundary between shaping and staging, before Chunking begins. **Output Review** closes the Stage loop after each prompt runs.

**Prompt Guard** catches what Prompt Craft missed — the prompt's own invisible decisions. **Live Mirror** catches what happened during the build. **Decision Capture** catches everything after.

---

## The Skill Structure

Each SKILL.md contains:

- **Frontmatter** — name and description for skill routing
- **Your Job** — one clear statement of what this skill does
- **Your Posture** — the voice and stance for this moment in the flow cycle
- **How to Receive What Lands** — what to do when the builder arrives with more or less than expected
- **The Core Method** — questions, layers, or steps specific to this skill
- **Output Structure** — what the response looks like, with P1/P2/P3 priority scoring where applicable
- **Output Formatting** — decorated titles, section markers, and branded footer for terminal scanability
- **Tone Reminders** — what to protect and what to avoid
- **Part of Stage Manager** — where this skill sits in the suite and how it relates to adjacent skills

---

## Repository Structure

```
install-enhanced-ce.sh                      ← one-command installer

plugins/stage-manager/skills/
  shape-find-holes/SKILL.md
  shape-collapsed-options/SKILL.md
  shape-risk-sequence/SKILL.md
  shape-soul-check/SKILL.md
  shape-to-stage-gate/SKILL.md
  stage-chunking/SKILL.md
  stage-wsjf/SKILL.md
  stage-prompt-craft/SKILL.md
  stage-prompt-guard/SKILL.md                ← new
  stage-live-mirror/SKILL.md                 ← new
  stage-output-review/SKILL.md
  stage-decision-capture/SKILL.md            ← new
  coherence-check/SKILL.md

plugins/compound-engineering/commands/ce/
  brainstorm.md                              ← enhanced with Stage Manager gates
  plan.md
  work.md
  review.md
  compound.md

plugins/shared/references/
  invention-zones.md
  tool-selection-zones.md
  breakthrough-dimensions.md

SOUL.md          ← the animating idea behind this library
README.md        ← this file
```

---

## The Soul Document

`SOUL.md` at the root of this repo is the animating idea behind Stage Manager — the mantra, the daily practice, the vision, and what this work is in service of. Read it before reading the skills. It's the context everything else runs through.

---

## Using These Skills

**With Claude Code (recommended)**

Run the installer above. All 13 skills appear as `/slash-commands` in Claude Code. The enhanced CE pipeline runs with Stage Manager gates built in.

**With Cursor, Replit, or any AI coding tool**

Reference a skill file in your project's instructions or rules file. The coding tool will load it as context for your session.

**With Claude or any AI assistant**

Paste a skill's contents into your system prompt or at the top of a conversation. Then describe what you're working on. The skill will shape how the AI responds to you.

**As a standalone practice**

Read a skill before starting work. Use it as a checklist or reflection guide. The questions are useful even without an AI.

---

## Made by Manifest AI

These skills are free and open. They are the first taste of deliberate unfolding — available to any builder, right now.

Start here. Feel what it's like to expand options before converging. Then come to Stage Manager for the full practice.

*For the builders who want to lead.*

> [manifest.ai](https://manifest.ai) · [Stage Manager Skills](https://github.com/Mnfst-AI/Stage_Manager_Skills)
