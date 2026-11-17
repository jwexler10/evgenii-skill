# Evgenii

**Price the outcome, the alternatives, and the uncertainty.**

An agent skill for economic decisions involving cost, pricing, resource allocation, provider selection, build-versus-buy, and incentives.

## What it does

- Chooses the economic unit that matches the outcome you actually need.
- Separates fixed, recurring, marginal, sunk, switching, and opportunity costs.
- Examines incentives, strategic reactions, and operational bottlenecks when relevant.
- Calculates break-even thresholds and tests which assumptions can reverse the recommendation.

A reasoning workflow, not a price feed or an executable calculator. Supply evidence or permit the agent to verify it; illustrative numbers are not market data.

## Install

This repository contains a portable, instruction-only agent skill. No API key,
MCP server, executable script, or companion skill is required. Tools are useful
when your task needs current information or inspection of an existing project.

1. Download this repository with **Code → Download ZIP**, or clone it:

   ```bash
   git clone https://github.com/jwexler10/evgenii-skill.git
   ```

2. For a Codex project, copy the entire `skills/evgenii` folder into the target
   project's `.agents/skills/` directory. The result should be:

   ```text
   your-project/
     .agents/
       skills/
         evgenii/
           SKILL.md
   ```

   Keep any supporting files inside that folder when copying. For user-wide local
   Codex discovery, use `~/.agents/skills/evgenii/` instead. Choose one scope to avoid
   installing duplicate copies.

3. In Codex, invoke the skill with `$evgenii` followed by your task, or let the
   agent select it when your task matches the description. If it does not appear,
   restart Codex. See the [official skills guide](https://learn.chatgpt.com/docs/build-skills).

For another agent that supports `SKILL.md`, use that agent's documented skills
directory. You can also explicitly ask an agent to read and apply
[`skills/evgenii/SKILL.md`](skills/evgenii/SKILL.md). Discovery and invocation syntax
depend on the host.

## Try it

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

- [`skills/evgenii/SKILL.md`](skills/evgenii/SKILL.md): the complete skill.
- [`LICENSE`](LICENSE): MIT license for these instructions and documentation.

Copyright © 2026 Jason Wexler.
