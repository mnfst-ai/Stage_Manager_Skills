# Stage Manager — Artful Making Skill Library

> **How you move through your work is what you build.**

A free, open collection of 13 skills for vibe coders who want to stay the author while building with AI tools.

These skills help you expand options before converging, maintain coherence across a build, and keep the soul of the work intact while Claude Code, Cursor, Replit, or any agentic coding tool runs at speed.

---

## Two Ways to Install

### Option A: Stage Manager Only

Use this if you just want the 13 Stage Manager skills as slash commands in Claude Code.

```bash
git clone https://github.com/Mnfst-AI/Stage_Manager_Skills.git
cd Stage_Manager_Skills
bash install.sh
```

This symlinks all skills to `~/.claude/skills/` and makes them available as `/slash-commands` in any Claude Code session.

### Option B: Stage Manager + Enhanced Compound Engineering

Use this if you want the full stack — Stage Manager skills plus the CE pipeline with Stage Manager gates woven into every phase.

**Works whether or not you already have Compound Engineering installed.** If CE is present, it backs up your originals. If CE is not present, it installs stock CE from [Every's repo](https://github.com/EveryInc/compound-engineering-plugin) first, then overlays the enhanced versions.

```bash
git clone -b enhanced-cli-skills https://github.com/Mnfst-AI/Stage_Manager_Skills.git
cd Stage_Manager_Skills
bash install-enhanced-ce.sh
```

The installer will:
- Install Compound Engineering from [EveryInc/compound-engineering-plugin](https://github.com/EveryInc/compound-engineering-plugin) if not already present
- Back up stock CE commands to `~/.claude/commands/ce.backup/`
- Overlay enhanced CE commands with Stage Manager gates at every phase
- Symlink all 13 Stage Manager skills
- Link shared reference files

To roll back to stock CE: `cp ~/.claude/commands/ce.backup/* ~/.claude/commands/ce/`

---

## What Is Compound Engineering?

[Compound Engineering](https://every.to/chain-of-thought/compound-engineering-how-every-codes-with-agents) is a methodology and Claude Code plugin from [Every](https://every.to), created by Kieran Klaassen and Dan Shipper. It inverts the typical accumulation of technical debt — each unit of engineering work makes the next unit easier by documenting bugs, failed tests, and problem-solving insights so future agents and team members can reuse them.

CE provides five commands that flow sequentially:

| CE Command | What It Does |
|---|---|
| `/ce:brainstorm` | Explore requirements and approaches through collaborative dialogue |
| `/ce:plan` | Transform feature descriptions into well-structured project plans |
| `/ce:work` | Execute work plans efficiently while maintaining quality |
| `/ce:review` | Exhaustive code reviews using multi-agent analysis and worktrees |
| `/ce:compound` | Document a solved problem to compound your team's knowledge |

The philosophy: roughly 80% of effort goes into planning and review, 20% into work and documentation.

Install CE first from [EveryInc/compound-engineering-plugin](https://github.com/EveryInc/compound-engineering-plugin), then run the Stage Manager enhanced installer above.

---

## What Stage Manager Adds to CE

Stage Manager doesn't replace CE — it adds shaping discipline and live feedback at every phase:

| CE Phase | Stage Manager Gate |
|---|---|
| **Brainstorm** | Coherence Check at close — confirms the brainstorm is still aligned before planning |
| **Plan** | Find the Holes + Risk Sequence — surfaces spec gaps and load-bearing assumptions before work begins |
| **Work** | Prompt Guard before coding, Live Mirror after each session — flags invisible decisions in real time |
| **Review** | Output Review + Decision Capture — three-layer review plus full manifest of tool-made choices |
| **Compound** | Soul Check — ensures the documented learning still reflects the original intent |

Original CE commands are preserved at `/ce.backup:*` and work exactly as before.

---

## The 13 Skills

### Shape Node

| Skill | Slash Command | What It Does |
|---|---|---|
| **Find the Holes** | `/shape-find-holes` | Maps every place in a spec where a coding tool will invent behavior you didn't ask for. P1/P2/P3 priority scoring. Interactive hole resolution. |
| **Collapsed Options** | `/shape-collapsed-options` | Finds decisions you already made without knowing it — especially where you're trying to do something different. P1/P2/P3 scoring. |
| **Risk Sequence** | `/shape-risk-sequence` | Surfaces load-bearing assumptions and sequences by cost-if-wrong. P1/P2/P3 scoring. Shows what to prove first. |
| **Soul Check** | `/shape-soul-check` | Deep 10-15 minute read on whether the original animating idea is still alive in the artifact. |

### Shape → Stage Transition

| Skill | Slash Command | What It Does |
|---|---|---|
| **Shape-to-Stage Gate** | `/sense-shape-to-stage-gate` | Five readiness questions before staging begins. Prevents premature staging and over-shaping. Verdicts: Ready, Almost, Not Yet. |

### Stage Node

| Skill | Slash Command | What It Does |
|---|---|---|
| **Chunking** | `/stage-chunking` | Breaks work into flow-cycle-sized pieces — each promptable, testable, and sequenced by cost of delay. |
| **Cost of Delay** | `/stage-wsjf` | Sequences stories by what it costs to wait — economic, risk, flow, and joy costs. H/M/L scoring. |
| **Prompt Craft** | `/stage-prompt-craft` | Turns a shaped chunk into a scoped, guardrailed prompt. P1/P2/P3 invention scoring. |
| **Prompt Guard** | `/stage-prompt-guard` | Reviews a crafted prompt before sending — flags every invisible decision the prompt itself is making. |
| **Live Mirror** | `/stage-live-mirror` | Compares plan vs. code output after a session. Surfaces every invisible decision the tool made. |
| **Output Review** | `/stage-output-review` | Three-layer review: definition of done, original intent, what it sets up next. Verdicts: Accept, Revise, Return. |
| **Decision Capture** | `/stage-decision-capture` | Full decisions-made manifest after a build — every choice the tool made that wasn't in the spec. |

### All Nodes

| Skill | Slash Command | What It Does |
|---|---|---|
| **Coherence Check** | `/coherence-check` | Lightweight 2-minute gate at any transition point. For deep artifact reads, use Soul Check. |

---

## How to Read the Suite

**Risk Sequence** retires load-bearing assumptions before building. Once assumptions are confirmed, **Cost of Delay** sequences the confirmed work.

**Find the Holes** maps gaps the AI will invent into. **Collapsed Options** maps decisions the builder already made without knowing it. Run both before staging.

**Soul Check** is a deep read on a single artifact — 10-15 minutes. **Coherence Check** is the lightweight transition gate — 2 minutes, any artifact, any moment of doubt.

**Shape-to-Stage Gate** runs once, at the boundary between shaping and staging. **Output Review** closes the Stage loop after each prompt runs.

**Prompt Guard** catches what Prompt Craft missed — the prompt's own invisible decisions. **Live Mirror** catches what happened during the build. **Decision Capture** catches everything after.

---

## The Flow Cycle

Stage Manager organizes the builder's work into three nodes:

**Shape** — exploring the problem space before converging on a solution
**Stage** — building in small, intentional increments with full agency
**All Nodes** — coherence checks that run at any transition point

The skills support every phase — and the transitions between them.

---

## Repository Structure

```
install.sh                                   ← standalone Stage Manager installer
install-enhanced-ce.sh                       ← Stage Manager + enhanced CE installer

plugins/stage-manager/skills/
  shape-find-holes/SKILL.md
  shape-collapsed-options/SKILL.md
  shape-risk-sequence/SKILL.md
  shape-soul-check/SKILL.md
  shape-to-stage-gate/SKILL.md
  stage-chunking/SKILL.md
  stage-wsjf/SKILL.md
  stage-prompt-craft/SKILL.md
  stage-prompt-guard/SKILL.md
  stage-live-mirror/SKILL.md
  stage-output-review/SKILL.md
  stage-decision-capture/SKILL.md
  coherence-check/SKILL.md

plugins/compound-engineering/commands/ce/    ← enhanced CE with Stage Manager gates
  brainstorm.md
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
- **Part of Stage Manager** — where this skill sits in the suite

---

## The Soul Document

`SOUL.md` at the root of this repo is the animating idea behind Stage Manager — the mantra, the daily practice, the vision, and what this work is in service of. Read it before reading the skills.

---

## Using These Skills

**With Claude Code (recommended)**

Run either installer above. All 13 skills appear as `/slash-commands` in Claude Code.

**With Cursor, Replit, or any AI coding tool**

Reference a skill file in your project's instructions or rules file. The coding tool will load it as context for your session.

**With Claude or any AI assistant**

Paste a skill's contents into your system prompt or at the top of a conversation. The skill will shape how the AI responds to you.

**As a standalone practice**

Read a skill before starting work. Use it as a checklist or reflection guide. The questions are useful even without an AI.

---

## Made by Manifest AI

These skills are free and open. They are the first taste of deliberate unfolding — available to any builder, right now.

The enhanced Compound Engineering integration is built on the excellent work of [Every](https://every.to) and their [Compound Engineering plugin](https://github.com/EveryInc/compound-engineering-plugin).

Start here. Feel what it's like to expand options before converging. Then come to Stage Manager for the full practice.

*For the builders who want to lead.*

> [manifest.ai](https://manifest.ai) · [Stage Manager Skills](https://github.com/Mnfst-AI/Stage_Manager_Skills)
