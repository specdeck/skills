---
name: specdeck-plan-build
description: "Read every feature specification that is ready to build, decide what each one builds on (a goal waits until the specifications it builds on are built; everything else runs in parallel), record that with set_spec_dependencies, and create each specification's goal in that order. Plans only, claims nothing. Run this once the specifications are written, before building, or whenever the plan needs redoing."
---

# Plan the build order

This skill runs a workflow that the SpecDeck MCP server serves. Call the server's `plan_build` tool and follow the steps it returns, exactly: they are the whole workflow, and the call itself changes nothing.

It takes no arguments.

If no SpecDeck MCP server is connected, or it has no `plan_build` tool, stop and tell the user to connect one first: https://specdeck.ai/docs/mcp-server/#agents
