# Evgenii

**Price the outcome, the alternatives, and the uncertainty.**

An agent skill for economic decisions involving cost, pricing, resource allocation, provider selection, build-versus-buy, and incentives.

## Install in one command

```bash
npx skills add jwexler10/evgenii-skill
```

Choose Claude Code, Cursor, Codex, or another supported agent in the installer.
Requires [Node.js](https://nodejs.org/) 22.20 or later. Installs to the current project
by default; add `--global` for a user-wide installation. See the
[skills CLI](https://github.com/vercel-labs/skills) for supported agents and options.

For a noninteractive installation to Claude Code, Cursor, and Codex together:

```bash
npx skills add jwexler10/evgenii-skill --skill evgenii --agent claude-code cursor codex --yes
```

Prefer a graphical install? Use the Claude marketplace option below.

## What it does

- Chooses the economic unit that matches the outcome you actually need.
- Separates fixed, recurring, marginal, sunk, switching, and opportunity costs.
- Examines incentives, strategic reactions, and operational bottlenecks when relevant.
- Calculates break-even thresholds and tests which assumptions can reverse the recommendation.

A reasoning workflow, not a price feed or an executable calculator. Supply evidence or permit the agent to verify it; illustrative numbers are not market data.

## Before vs. after

**Example request:** “Service A is cheaper per attempt. Service B costs more but has fewer failures. Which should we use?”

| Aspect | Without the skill: illustrative pitfall | With Evgenii: intended behavior |
|---|---|---|
| Unit | Ranks the services by advertised price per request. | Compares the unit that matters: successful outcomes, with comparable workloads and success definitions. |
| Cost | Considers only recurring vendor charges. | Includes switching, operations, failure losses, and the opportunity cost of engineering attention. |
| Decision | Says quality costs more without pricing the tradeoff. | Calculates a break-even threshold and identifies which uncertain input can reverse the ranking. |

These are illustrative comparisons, not recorded model outputs or benchmark results.
Actual results depend on the model, the prompt, and the evidence you provide.

## Install as a Claude plugin

This repository is both a standalone skill and a single-plugin marketplace. The
plugin and the skills CLI install the same `SKILL.md`; choose one route per host
to avoid duplicate installations.

### Claude and Cowork: no terminal

1. Open **Plugins** (or **Customize → Plugins**, depending on your version).
2. Choose **Add → Add marketplace → Add from a repository**.
3. Enter `jwexler10/evgenii-skill` or `https://github.com/jwexler10/evgenii-skill`.
4. Select **Evgenii** and add the plugin. Find its skill through `/` or the
   skill picker; when namespaced commands are shown, use `/evgenii:evgenii`.

Availability and organization controls depend on your Claude plan and account.
See [Anthropic's plugin installation guide](https://support.claude.com/en/articles/13837440-use-plugins-in-claude).

### Claude Code: marketplace commands

Run these inside Claude Code:

```text
/plugin marketplace add jwexler10/evgenii-skill
/plugin install evgenii@jwexler10-evgenii
```

Then invoke `/evgenii:evgenii` followed by your task. The marketplace is defined in
[`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json), and the plugin
in [`.claude-plugin/plugin.json`](.claude-plugin/plugin.json).

### Manual installation

Download the repository using **Code → Download ZIP**, or clone it:

```bash
git clone https://github.com/jwexler10/evgenii-skill.git
```

Copy the entire `skills/evgenii` folder, including any supporting files, into the
appropriate directory in your target project:

| Agent | Project skill directory | Invocation |
|---|---|---|
| Claude Code, direct skill | `.claude/skills/evgenii/` | `/evgenii` |
| Codex | `.agents/skills/evgenii/` | `$evgenii` |
| Cursor | `.cursor/skills/evgenii/` | Ask the agent to use Evgenii. |

Each destination must contain `SKILL.md` directly. Other hosts may use different
discovery or invocation rules; follow their documentation. See the
[Codex skills guide](https://learn.chatgpt.com/docs/build-skills).

This is an instruction-only skill: no API key, MCP server, companion skill, or
executable script is required. Tools are useful when your actual task needs live
information or inspection of an existing project.

## Try it

The prompts below use Codex's `$evgenii` syntax. In Claude Code, use `/evgenii` for a
direct skills installation or `/evgenii:evgenii` for a marketplace plugin. In Cursor,
ask the agent to use Evgenii and give it the same task.


```text
$evgenii Compare building an internal scheduling tool with buying a service. Include engineering attention and switching costs.
```

```text
$evgenii Service A is cheaper per attempt, but service B has fewer failures. Compare cost per successful outcome and the incremental break-even threshold.
```

```text
$evgenii Evaluate annual versus monthly supplier contracts. Show the utilization and price assumptions that change the answer.
```

Expect dated evidence, explicit assumptions, comparable costs and benefits, sensitivity analysis where useful, and a reversible next action when possible.

## Adapt it

Supply your actual objective, constraints, evidence, and priorities. Edit the skill
to fit your workflow. It assumes no particular product, repository structure,
technology stack, or internal decision log. Applying a thinking skill does not
itself authorize changes, purchases, deployments, or other external actions.

## Repository contents

- [`.claude-plugin/plugin.json`](.claude-plugin/plugin.json): Claude plugin metadata.
- [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json): installable marketplace catalog.
- [`skills/evgenii/SKILL.md`](skills/evgenii/SKILL.md): the complete skill.
- [`LICENSE`](LICENSE): MIT license for these instructions and documentation.

Copyright © 2026 Jason Wexler.
