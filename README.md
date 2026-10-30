# Legal research assistant for asylum counseling

This repository contains the instructions of an AI legal research assistant that we designed, piloted and refined with asylum counselors at Caritas Switzerland. It accompanies the upcoming paper *Agentic AI-augmented legal research in asylum counseling: An action design research study*.

The assistant answers counselors' questions about Swiss asylum law. It searches Swiss legislation and case law through two public legal databases, consults international and country-of-origin sources on the web, and backs each important claim with a linked reference. It is a research aid for legal professionals, who remain responsible for checking every reference before relying on it.

## Contents

| File | Description |
|---|---|
| `agent_prompt.txt` | Instructions for the custom agent. |
| `recherche-asile/` | The instructions adapted as a skill (`SKILL.md`, plus metadata and an icon), so that they also apply in ordinary chats. |
| `recherche-asile.zip` | The skill as a zip file, ready to import. |
| `MCPs/` | Exports of the two database connectors as ChatGPT plugins (`Entscheidsuche.zip`, `OpenCaseLaw.zip`), with an icon for each. |

The icons in `MCPs/` remain the property of Entscheidsuche.ch and OpenCaseLaw.ch.

## Data sources

The assistant uses two public Swiss legal databases through their MCP servers:

| Database | Content | MCP server URL |
|---|---|---|
| [Entscheidsuche.ch](https://entscheidsuche.ch) | Decisions of Swiss courts | `https://mcp.entscheidsuche.ch/mcp` |
| [OpenCaseLaw.ch](https://opencaselaw.ch) | Swiss legislation, case law, and related material | `https://mcp.opencaselaw.ch` |

## How it works

The assistant comes in two forms, both built on ChatGPT:

- **A custom agent** that combines the instructions in `agent_prompt.txt`, both database connectors, and web search. The agent works on a task for longer before answering, which gives more thorough results but takes more time and uses more of the account's usage quota. It suits complex research.
- **The skill**, for frequent and simpler questions in ordinary chats. The model loads it automatically when a question concerns law, asylum, or a country situation.

## Recreating a similar setup

Custom agents are currently only available in ChatGPT Business and Enterprise workspaces. You can get a close approximation in other ChatGPT accounts, or in other AI platforms that support skills and MCP servers:

1. **Import the skill** from `recherche-asile.zip` (or the `recherche-asile/` folder).
2. **Add both MCP servers** listed above as custom connectors, without authentication. You can import the exports in `MCPs/`, or add the servers manually with the URLs above and the icons in `MCPs/`.
3. **Ask your question in a mode that lets the model work longer** (in ChatGPT, at the time of writing, the "Work" mode), with the skill and both connectors selected.

Menu names and features change frequently, so check your platform's current documentation for the exact steps.

## Adapting the instructions

The instructions are specific to asylum counselors in Switzerland. To adapt them to another context, edit in particular:

- the description of the user and their work (first paragraph),
- the language of the answers,
- the lists of databases and web sources, and the rules for which sources to prefer.

## Responsible use

- Use the assistant only for general legal questions and research. Never enter personal, confidential, or otherwise sensitive data about clients.
- Check every reference before relying on it. The assistant can cite wrong or outdated sources.
- The assistant supports professional judgment; it does not replace it and does not provide legal advice.
