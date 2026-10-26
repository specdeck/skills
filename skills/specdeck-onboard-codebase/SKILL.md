---
name: specdeck-onboard-codebase
description: "Read the code in the current working directory and turn it into SpecDeck specs: the system's areas, then foundational docs, then a build-first Platform spec for the greenfield bootstrap and a spec for every feature, so the result is enough to rebuild the system from scratch. By default (mode plan) it gets your plan approved once, then writes everything without stopping; set mode autonomous to skip even that. Specs land as proposals you review in the web app (output propose) unless you set output publish to publish them directly. Run this once when adopting SpecDeck on a project that has no specs yet."
---

# Onboard an existing codebase into SpecDeck

This skill runs a workflow that the SpecDeck MCP server serves. Call the server's `onboard_codebase` tool and follow the steps it returns, exactly: they are the whole workflow, and the call itself changes nothing.

Settle its arguments from the user's request. Leave out one the request does not name, and the tool uses its default:

- mode (plan or autonomous): plan (default): stop once after the plan for approval, then write everything without stopping again. autonomous: run start to finish without stopping.
- output (propose or publish): propose (default): each spec lands as a proposal you review and publish in the web app -- safe and reversible. publish: each spec goes live immediately via publish_draft, with no review queue.

If no SpecDeck MCP server is connected, or it has no `onboard_codebase` tool, stop and tell the user to connect one first: https://specdeck.ai/docs/mcp-server/#agents
