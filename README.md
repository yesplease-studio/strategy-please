<img width="1584" height="396" alt="Github-strategy-please" src="https://github.com/user-attachments/assets/e3f12ac8-d392-40d5-8b8c-9337c1b20973" />

# strategy-please

An open-source, AI-native workshop recommendation engine for strategic planning.

Takes challenges, questions, and objectives as input. Recommends the right workshop to run, with the key questions to ask and the outputs to expect.

Built on the strategic maturity framework from [Yes Please Studio](https://yesplease.studio). The system tells you *what* to run and *why*. Human facilitation is where practitioners add value.

## How it works

Most workshop resources are browsable catalogs. strategy-please is a **diagnostic-to-prescription pipeline**:

1. **Start from the problem, not the format.** "We don't know who our best customer is" maps to ICP Discovery Workshop, not "browse our list."
2. **Map to strategic maturity dimensions.** Each workshop addresses specific dimensions at specific maturity levels.
3. **Scale facilitation difficulty.** Some workshops are self-facilitatable with the guide. Others benefit from (or require) an experienced facilitator.
4. **Chain workshops into programs.** A company with multiple gaps gets a sequenced recommendation, not a pile of suggestions.

## Who this is for

- **Founders and operators** who know something is off but don't know which conversation to have
- **Consultants and facilitators** who want a structured recommendation framework they can build on
- **Teams** who need to align on strategic fundamentals before making big decisions

## Quickstart

1. Open this repo in [Claude Code](https://claude.ai/code)
2. Claude will detect `CLAUDE.md` and load the system
3. If this is your first time, say **"help me set up"** and Claude will walk you through creating a company profile
4. Once your profile exists, try: **"What workshop should we run?"** or **"We don't know who our best customer is"**

Or skip the profile and go straight to the catalog: browse `workshops/` to see what's available.

## Workshop catalog

| Workshop | Primary dimension | Format | Facilitation |
|----------|------------------|--------|-------------|
| [Strategic Clarity](workshops/ws-strategic-clarity.md) | Strategic Clarity | Half-day | Guided |
| [ICP Discovery](workshops/ws-icp-discovery.md) | ICP Definition and Focus | 90 min | Self-serve / Guided |
| [Positioning](workshops/ws-positioning.md) | Positioning and Messaging | Half-day | Guided |
| [Pricing Strategy](workshops/ws-pricing-strategy.md) | Revenue Model and Pricing | 90 min | Guided |
| [Content Strategy](workshops/ws-content-strategy.md) | Content and Thought Leadership | 90 min | Guided |
| [Sales Process](workshops/ws-sales-process.md) | Sales Process and Conversion | 90 min | Guided |
| [Competitive Landscape](workshops/ws-competitive-landscape.md) | Competitive Awareness | 90 min | Self-serve / Guided |
| [Growth Channel](workshops/ws-growth-channel.md) | Growth Engine and Distribution | 90 min | Guided |
| [Stakeholder Alignment](workshops/ws-stakeholder-alignment.md) | Cross-cutting (Dims 1-3) | 60 min | Self-serve / Guided |
| [Assumption Mapping](workshops/ws-assumption-mapping.md) | Cross-cutting | 90 min | Self-serve |

## The eight dimensions

The workshop catalog maps to a strategic maturity framework with eight dimensions:

| # | Dimension | The question it answers |
|---|-----------|----------------------|
| 1 | Strategic Clarity | Why do we exist, who do we serve, where are we going? |
| 2 | Positioning and Messaging | Can we explain what we do in customer terms? |
| 3 | ICP Definition and Focus | Do we know who our best customers are? |
| 4 | Revenue Model and Pricing | Do we have a defensible way of making money? |
| 5 | Content and Thought Leadership | Do we systematically demonstrate expertise? |
| 6 | Sales Process and Conversion | Do we have a repeatable way of turning interest into revenue? |
| 7 | Competitive Awareness | Do we know where we win and lose? |
| 8 | Growth Engine and Distribution | Do we have a scalable way of reaching our ICP? |

All eight dimensions are covered by at least one workshop.

## The open-source / consulting boundary

The **recommendation engine** is the open-source value: what workshop to run, why, what questions to ask, what outputs to expect.

The **facilitation itself** (running the room, reading the dynamics, knowing when to push and when to hold space) is the practitioner's edge. strategy-please makes the case for the workshop. The facilitator makes the workshop work.

## The "-please" family

Open-source, AI-native tools for strategic and product work by [Yes Please Studio](https://yesplease.studio):

| Tool | What it does |
|------|-------------|
| **strategy-please** (this repo) | Maps challenges to the right workshop using a strategic maturity framework |
| **[prd-please](https://github.com/yesplease-studio/prd-please)** | Structured methodology for AI-native product requirements |
| **[sales-please](https://github.com/yesplease-studio/sales-please)** | Lightweight deal qualification framework built on WORTH |

Each tool works standalone. Fork it, open Claude Code, start working.

## Workflows

Pre-defined workshop sequences for common situations:

| Workflow | What it does |
|----------|-------------|
| [New Engagement](workflows/new-engagement.yaml) | Full recommend → design → run → debrief cycle |
| [Strategic Foundations](workflows/strategic-foundations.yaml) | Three-workshop chain: Clarity → ICP → Positioning |
| [Growth Readiness](workflows/growth-readiness.yaml) | Two-workshop chain: Competitive → Growth Channel |
| [Full Diagnostic](workflows/full-diagnostic.yaml) | Assessment-driven: score all dimensions, then prescribe |

## Examples

See [`examples/nordflow-full-flow.md`](examples/nordflow-full-flow.md) for a complete fictional walkthrough: onboarding → recommendation → session design → workshop → debrief.

## Contributing

Workshop contributions welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines, or use the `workshop-author` skill to create new entries interactively.

## License

Apache 2.0
