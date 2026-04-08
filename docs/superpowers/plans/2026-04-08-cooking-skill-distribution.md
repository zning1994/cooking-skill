# Cooking Skill Distribution Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Improve `cooking.skill` distribution quality by adding examples, lightweight eval assets, README upgrades, and repository consistency checks without changing the core cooking logic.

**Architecture:** Build outward from the current skill core. Add visible repo assets first (`examples/`, `evals/`), then tighten the main README around those assets, then run a consistency pass across metadata and localized docs.

**Tech Stack:** Markdown, JSON, YAML

---

### Task 1: Create distribution-facing example assets

**Files:**
- Create: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/examples/basic-flows.md`
- Create: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/examples/demo-prompts.md`

- [ ] **Step 1: Write `basic-flows.md`**

Include one compact example each for:
- craving mode
- ingredient mode
- specific dish / technique mode

- [ ] **Step 2: Write `demo-prompts.md`**

Include copy-ready prompts grouped by:
- cravings
- ingredients
- techniques
- substitutions

- [ ] **Step 3: Verify readability**

Run:
`sed -n '1,240p' /Users/zning/LocalCodes/wangchenmoji/cooking.skill/examples/basic-flows.md`
`sed -n '1,220p' /Users/zning/LocalCodes/wangchenmoji/cooking.skill/examples/demo-prompts.md`

Expected: examples are short, scannable, and consistent with the current skill behavior.

### Task 2: Add lightweight evaluation anchors

**Files:**
- Create: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/evals/evals.json`

- [ ] **Step 1: Define a minimal eval schema**

Use a simple JSON structure with:
- `name`
- `input`
- `expected_behavior`
- optional `mode`

- [ ] **Step 2: Add representative cases**

Include at least:
- craving recommendation case
- ingredient recommendation case
- technique answer case
- substitution answer case

- [ ] **Step 3: Verify JSON parses**

Run:
`jq . /Users/zning/LocalCodes/wangchenmoji/cooking.skill/evals/evals.json`

Expected: valid JSON output.

### Task 3: Strengthen the main README for distribution

**Files:**
- Modify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README.md`

- [ ] **Step 1: Add clearer distribution framing**

Add or tighten:
- what this is
- what this is not
- best at / not for yet

- [ ] **Step 2: Link the new example assets**

Surface:
- `examples/basic-flows.md`
- `examples/demo-prompts.md`

- [ ] **Step 3: Keep install paths prominent**

Ensure:
- `npx skills add`
- `openclaw skills install`
- manual clone install

remain easy to find near the top.

### Task 4: Sync localized docs only where needed

**Files:**
- Modify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README_EN.md`
- Modify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README_JA.md`
- Modify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README_ES.md`
- Modify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README_DE.md`
- Modify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README_KO.md`
- Modify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README_PT.md`
- Modify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README_RU.md`

- [ ] **Step 1: Update only required distribution surfaces**

Keep aligned:
- install commands
- project identity
- example links if surfaced globally

- [ ] **Step 2: Avoid full-content rewrite**

Do not over-expand localized READMEs in this phase unless the main README changes require it.

### Task 5: Consistency pass across skill metadata

**Files:**
- Verify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/SKILL.md`
- Verify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/agents/openai.yaml`
- Verify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/.clawhubignore`
- Verify: `/Users/zning/LocalCodes/wangchenmoji/cooking.skill/README.md`

- [ ] **Step 1: Re-read metadata surfaces**

Check:
- naming
- install identity
- homepage references
- phrasing consistency

- [ ] **Step 2: Verify repository structure**

Run:
`find /Users/zning/LocalCodes/wangchenmoji/cooking.skill -maxdepth 2 -type f | sort`

Expected: new `examples/` and `evals/` assets appear in the repository.

### Task 6: Final verification and release readiness check

**Files:**
- Verify all changed files in the repo

- [ ] **Step 1: Read the final README and example assets**

Run:
`sed -n '1,260p' /Users/zning/LocalCodes/wangchenmoji/cooking.skill/README.md`
`sed -n '1,240p' /Users/zning/LocalCodes/wangchenmoji/cooking.skill/examples/basic-flows.md`
`sed -n '1,220p' /Users/zning/LocalCodes/wangchenmoji/cooking.skill/examples/demo-prompts.md`

- [ ] **Step 2: Verify eval JSON**

Run:
`jq . /Users/zning/LocalCodes/wangchenmoji/cooking.skill/evals/evals.json`

- [ ] **Step 3: Check git diff scope**

Run:
`git -C /Users/zning/LocalCodes/wangchenmoji/cooking.skill status -sb`

Expected: only intended distribution-phase files changed.

- [ ] **Step 4: Report remaining gaps honestly**

Call out that phase 1 improves packaging and discoverability, but does not yet deepen cooking capability.
