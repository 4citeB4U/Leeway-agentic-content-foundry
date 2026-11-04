# Beast AI Agentic Content Foundry

Beast AI Agentic Content Foundry is an AI-first orchestration product for converting source content into multi-platform publishing pipelines, with Agent Lee as the execution persona and Leeway governance controls embedded in runtime.

## Executive Summary

- Product: Beast AI Agentic Content Foundry
- Persona: Agent Lee
- Author: Leonard Le
- Stack: React 19 + Vite 6 + TypeScript + Tailwind v4
- Core capability: Build, route, and execute node-based content workflows from source to distribution

## Why This Matters

For developers:

- Clear local setup and governed build pipeline
- Extensible node and platform model
- Runtime manifests for HiveMind orchestration and platform API skills

For investors:

- Productized orchestration UI, not just a script-based prototype
- Governance-backed execution controls and brand gate enforcement
- Platform deployment readiness model with documentation-grounded skills
- Clear path from content production to social distribution automation

## Current State (November 2026)

- Branding and product framing set to Beast AI Agentic Content Foundry
- Agent Lee orchestration lane supports:
   - `auto` (hybrid)
   - `hivemind` (manifest-based)
   - `gemini` (provider-first with fallback)
- Platform API skill manifest generation implemented (`public/platform-api-skills.json`)
- Content Vault is the project working set between source inputs, Continuum references, Office Suites, and Leeway IDE
- Workspace state persists locally with project identity, nodes, edges, artifacts, settings, camera, and staged handoffs
- Office Suites and Leeway IDE handoffs produce portable `leeway.handoff.v1` JSON packets and retain a receipt artifact in the Vault
- Run Routine executes the local workflow preview in dependency order and saves an evidence manifest; platform nodes remain explicitly `prepared / connector pending` until a real connector returns evidence
- UI improvements completed:
   - Collapsed-node connection alignment
   - Color-coded connection lines by action/category
   - Content Wallet renamed to Content Vault
   - Header/hero/right-panel logo and targeted-training messaging updates

See full state snapshot in [docs/CURRENT_STATE.md](docs/CURRENT_STATE.md).

## Documentation Index

- Developer guide: [docs/DEVELOPER_GUIDE.md](docs/DEVELOPER_GUIDE.md)
- Investor overview: [docs/INVESTOR_OVERVIEW.md](docs/INVESTOR_OVERVIEW.md)
- Current state and roadmap: [docs/CURRENT_STATE.md](docs/CURRENT_STATE.md)

## Local Setup

Prerequisites:

- Node.js 20+
- npm 10+

Install and run:

```bash
npm install
npm run dev
```

Optional environment configuration (`.env.local`):

```env
GEMINI_API_KEY=your_key_here
VITE_AGENTLEE_AI_MODE=auto
```

Dev server runs on port `7007`.

## Key Scripts

- `npm run dev`: Sync manifests and launch local app
- `npm run build`: Sync manifests, brand-check, and create production build
- `npm run hivemind:sync`: Build HiveMind runtime manifest
- `npm run platform:skills`: Build platform API skills manifest
- `npm run brand:check`: Validate branding/governance constraints

## Runtime Architecture

1. Source inputs and transforms are represented as workflow nodes.
2. The Content Vault keeps project artifacts, handoff packets, and run evidence together as the working set.
3. Agent Lee maps intent to node sequences and the local runner follows dependency order.
4. HiveMind manifest contributes intent routing and roster metadata.
5. Handoff packets preserve project, artifact, provenance, and acceptance criteria for Office Suites or Leeway IDE.
6. Platform API skills provide deployment-grounded requirements; external publishing is only claimed after connector evidence.

## Governance And Standards

- Standards root: `LeeWay-Standards/`
- Primary runtime policy: `LeeWay-Standards/.leeway/layer-policy.json`
- App governance profile: `governance/leeway-application-governance.json`

The current browser implementation uses local storage and portable packet downloads until an authorized shared Continuum/Runtime Fabric adapter is connected. The UI deliberately labels that boundary instead of implying that external execution already occurred.

## CI/CD (GitHub Actions)

Top-level CI workflow is provided in [\.github/workflows/ci.yml](.github/workflows/ci.yml) and performs:

- dependency installation
- production build
- artifact upload (`dist/`)

This validates merge readiness for repository collaborators and external reviewers.

## License

This repository includes an MIT License in [LICENSE](LICENSE).
