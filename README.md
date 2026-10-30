# Assignment 3 — End-to-End Google ADK Agent Applications

**Due:** Thursday, Oct 29, 2026, 11:59 PM
**Submission:** GitHub repo URL (website URL field)
**Author:** Yashaswini Dinesh — yashaswini.dinesh@sjsu.edu

## Overview

Five Google Agent Development Kit (ADK) agents, each built end-to-end with code, documentation, and a walkthrough video.

| # | Agent | Folder | Reference |
|---|-------|--------|-----------|
| a | Deep Research Agent for Lead Generation | [`a-lead-generation-agent/`](./a-lead-generation-agent) | [Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/build-a-deep-research-agent-with-google-adk) · [sample repo](https://github.com/MagnIeeT/leadGenerationAgentADK) |
| b | Advanced Tool Agent using Gemini CLI inside an ADK pipeline | [`b-gemini-cli-tool-agent/`](./b-gemini-cli-tool-agent) | [Medium article](https://medium.com/@derrickchwong/combine-adk-gemini-cli-and-cloud-run-c5dea5118853) · [sample repo](https://github.com/derrickchwong/gemini-cli-on-adk) |
| c | MCP Tools-based Agent for Bug Assistance | [`c-mcp-bug-assistant/`](./c-mcp-bug-assistant) | [Google Cloud blog](https://cloud.google.com/blog/topics/developers-practitioners/tools-make-an-agent-from-zero-to-assistant-with-adk) · [sample code](https://github.com/google/adk-samples/tree/main/python/agents/software-bug-assistant) |
| d | Production-Quality Code Review Assistant | [`d-code-review-assistant/`](./d-code-review-assistant) | [Codelab](https://codelabs.developers.google.com/adk-code-reviewer-assistant/instructions?hl=en#0) · [sample repo](https://github.com/ayoisio/adk-code-review-assistant) |
| e | Production-Quality E-Commerce Agent | [`e-ecommerce-agent/`](./e-ecommerce-agent) | [Codelab](https://codelabs.developers.google.com/codelabs/sports-agent-adk-mcp-alloydb?hl=en#8) · [sample repo](https://github.com/mtoscano84/sports-agent-adk-mcp-alloydb) |

## Repository Structure

Each agent folder follows the same layout:

```
<agent-folder>/
├── src/        # agent source code
├── docs/       # setup notes, architecture, execution walkthrough
└── artifacts/  # screenshots, logs, sample outputs, test runs
```

## Video Walkthrough

🎥 **YouTube link:** _TODO — add combined or per-agent walkthrough video link(s) here_

| Agent | Video |
|-------|-------|
| a — Lead Generation | _TBD_ |
| b — Gemini CLI Tool Agent | _TBD_ |
| c — MCP Bug Assistant | _TBD_ |
| d — Code Review Assistant | _TBD_ |
| e — E-Commerce Agent | _TBD_ |

## Status

All 5 agents have real, working `google-adk` code in `src/agent.py` — not stubs:

| Agent | Code | Import-tested | Tool logic verified locally |
|---|---|---|---|
| a — Lead Gen | 3-stage `SequentialAgent` (plan → research → synthesize) | ✅ | search tool needs live API key |
| b — Gemini CLI | `LlmAgent` + CLI-as-tool via subprocess | ✅ | ✅ (error-handling path confirmed) |
| c — MCP Bug Assistant | `LlmAgent` + `MCPToolset` (filesystem) + ticket tools | ✅ | ✅ (ticket-store tools) |
| d — Code Review | 3-stage pipeline (ruff → LLM review → report) | ✅ | ✅ (ruff run against real + flawed code) |
| e — E-Commerce | `LlmAgent` + 5 tools (search/cart/checkout) | ✅ | ✅ (full search→cart→checkout flow) |

**What's still needed before final submission:** a Gemini API key to run the
LLM-level conversations end-to-end (none was available in the build
environment), the YouTube walkthrough video(s), and a push to your own GitHub
account. See each agent's `docs/README.md` for exact setup/run commands and
its specific checklist.

## Setup (per agent)

```bash
cd <agent-folder>
pip install -r requirements.txt
export GOOGLE_API_KEY=<your Gemini API key>
adk run src
```

Each `docs/README.md` has agent-specific prerequisites (e.g. Node/npx for
the MCP agent, the `gemini` CLI for agent b, `ruff` for agent d) and example
prompts to try.

## Publishing to your GitHub

This folder is already a local git repo with one commit. To publish:
```bash
gh repo create <your-repo-name> --public --source=. --remote=origin --push
# or: git remote add origin <your-repo-url> && git push -u origin main
```
