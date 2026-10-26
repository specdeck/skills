# SpecDeck skills

[SpecDeck](https://specdeck.ai) holds what to build and decides when work is
done. This repository packages the SpecDeck workflows for coding agents: a
Codex plugin that connects Codex to the SpecDeck MCP server, and three skills
that also install on their own.

| Skill | What it does |
| --- | --- |
| `specdeck-onboard-codebase` | Turns the code in the working directory into SpecDeck specifications. |
| `specdeck-plan-build` | Records what each ready specification builds on and creates the goals in that order. |
| `specdeck-install-agents-md` | Installs or updates the Working with SpecDeck section in AGENTS.md. |

Each skill calls the SpecDeck MCP server tool of the same name, which returns
the steps to follow. The steps live on the server, so they improve without a
reinstall.

## Codex

```sh
codex plugin marketplace add specdeck/skills
codex plugin add specdeck@specdeck
```

Or run `/plugins` in Codex and install SpecDeck from there. Start a new
session afterwards, then ask in plain words ("onboard this codebase into
SpecDeck") or pick a skill with `$`.

The plugin configures the SpecDeck MCP server at `https://app.specdeck.ai/mcp`.
If the SpecDeck tools are missing in the new session, add the server yourself
and sign in to the workspace you want Codex to work in:

```sh
codex mcp add specdeck --url https://app.specdeck.ai/mcp
codex mcp login specdeck
```

To update, run `codex plugin marketplace upgrade specdeck`.

## Other agents

```sh
npx skills add specdeck/skills
```

The skills need the SpecDeck MCP server connected to your agent: see
[Connect an agent](https://specdeck.ai/docs/mcp-server/#agents). Update them
with `npx skills update`.

Claude Code needs no skills: the SpecDeck MCP server serves the same
workflows as prompts, such as `/mcp__specdeck__onboard_codebase`.

## Support

Questions and bug reports go to hello@specdeck.ai.
