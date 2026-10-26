---
name: specdeck-install-agents-md
description: "Install or update a Working with SpecDeck section in this repository's AGENTS.md, or in another file you name (for example CLAUDE.md): how a coding agent claims goals, keeps status in SpecDeck, proves acceptance criteria with test runs, asks questions and proposes spec changes through SpecDeck. It shows the exact change and waits for your yes before writing anything. Run it once per repository, and again after a SpecDeck update to refresh the section; a re-run replaces the section in place."
---

# Install SpecDeck instructions in AGENTS.md

This skill runs a workflow that the SpecDeck MCP server serves. Call the server's `install_agents_md` tool and follow the steps it returns, exactly: they are the whole workflow, and the call itself changes nothing.

Settle its arguments from the user's request. Leave out one the request does not name, and the tool uses its default:

- file (text): File to write, relative to the repository root. Defaults to AGENTS.md; pass CLAUDE.md or any other agent instructions file instead.

If no SpecDeck MCP server is connected, or it has no `install_agents_md` tool, stop and tell the user to connect one first: https://specdeck.ai/docs/mcp-server/#agents
