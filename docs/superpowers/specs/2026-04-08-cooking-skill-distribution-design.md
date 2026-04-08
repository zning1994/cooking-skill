# Cooking Skill Distribution Design

**Date:** 2026-04-08  
**Workspace:** `/Users/zning/LocalCodes/wangchenmoji/cooking.skill`

## Goal

Ship a phase-1 iteration for `cooking.skill` that improves distribution, discoverability, and installation confidence without changing the core cooking logic.

This phase should make the repository feel like a complete, installable, and demoable skill project.

## Scope

### In scope

- Improve repository presentation for first-time visitors
- Add concrete examples so users can immediately see how the skill behaves
- Add lightweight evaluation assets to anchor future iteration
- Tighten consistency across `README`, `SKILL.md`, metadata, and install paths
- Keep `npx skills add` and OpenClaw install paths clearly documented

### Out of scope

- Expanding cuisine coverage
- Adding Western cooking knowledge
- Deepening the technique framework
- Rewriting skill behavior
- Building automation or packaging scripts

## Product Shape

Phase 1 is a distribution and packaging pass, not a capability expansion pass.

The repository should answer these questions quickly:

1. What does this skill do?
2. How do I install it?
3. What kinds of requests does it handle well?
4. What will the output actually look like?
5. Is this project structured enough to evolve further?

## Proposed Deliverables

### 1. Example assets

Add an `examples/` directory with:

- `basic-flows.md`
  A compact walkthrough of the three core entry paths:
  - craving mode
  - ingredient mode
  - specific dish / technique mode

- `demo-prompts.md`
  A copy-ready prompt list for demos, social sharing, and marketplace browsing.

Purpose:

- reduce imagination cost for first-time readers
- give README concrete anchors
- create reusable demo material

### 2. Lightweight eval asset

Add `evals/evals.json` with a small set of structured cases.

This should not be a full benchmark system yet. It should only provide a stable target for future iteration.

Suggested case groups:

- craving -> dish recommendation
- ingredient bundle -> dish recommendation
- technique question -> direct answer
- substitution question -> workaround answer

### 3. README strengthening

Update the Chinese main README first, and only make matching changes to localized README files where the content must stay aligned.

Key changes:

- move “quick install” closer to the top
- add clearer “what this is / what this is not”
- link to `examples/`
- add a short “best at / not for yet” section

### 4. Repository consistency pass

Ensure alignment across:

- `README.md`
- localized README files
- `SKILL.md`
- `agents/openai.yaml`
- `.clawhubignore`

This phase should reduce mismatch risk between what the repo promises and what the skill actually contains.

## Information Architecture

The post-iteration repository should look roughly like:

```text
cooking.skill/
├── README.md
├── README_EN.md
├── README_JA.md
├── README_ES.md
├── README_DE.md
├── README_KO.md
├── README_PT.md
├── README_RU.md
├── SKILL.md
├── LICENSE
├── .clawhubignore
├── agents/
│   └── openai.yaml
├── references/
│   ├── style-guide.md
│   ├── cooking-framework.md
│   └── techniques.md
├── examples/
│   ├── basic-flows.md
│   └── demo-prompts.md
└── evals/
    └── evals.json
```

## Design Decisions

### Decision 1: Examples before deeper docs

Examples provide more distribution value right now than more theory.
The skill already has enough internal reference material to explain itself; what it lacks is visible proof.

### Decision 2: Lightweight evals, not evaluation infrastructure

The first iteration should create a stable target, not a complicated system.
`evals/evals.json` is enough for now.

### Decision 3: Chinese README remains the primary distribution surface

The repo’s main audience is still Chinese-speaking.
Localized READMEs should stay in sync on install and identity, but they do not need full parity on every distribution flourish in phase 1.

## Risks

1. **Over-investing in polish before examples exist**
   Mitigation: create `examples/` first, then wire README to them.

2. **README promises getting ahead of actual capability**
   Mitigation: add a clear “best at / not for yet” boundary section.

3. **Localized docs drifting from main README**
   Mitigation: restrict required sync to install, title/header, and project identity.

4. **Evals becoming pseudo-tests without clear usage**
   Mitigation: keep evals lightweight and descriptive for now.

## Acceptance Criteria

Phase 1 is complete when:

- the repo contains visible `examples/`
- the repo contains a basic `evals/evals.json`
- the main README clearly explains install, use, examples, and current boundaries
- a new visitor can understand the project in under 10 seconds and find demo prompts in under 30 seconds

## Next Phase

After this phase lands, the next iteration should focus on actual cooking capability:

- sauces
- dish libraries
- more structured response coverage
- broader question handling
