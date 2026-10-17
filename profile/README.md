![Apex AI Academy: Co-Learn with your Agent](https://raw.githubusercontent.com/ApexAI-Academy/.github/main/assets/banner.svg)

[![Website](https://img.shields.io/badge/Website-Apex_AI_Academy-cbff56?style=flat-square)](https://apexai.academy/)
[![Public API](https://img.shields.io/badge/API-no_key_needed-cbff56?style=flat-square)](https://apexai.academy/llms.txt)
[![MCP](https://img.shields.io/badge/MCP-streamable_HTTP-cbff56?style=flat-square)](https://apexai.academy/developers/)
[![License](https://img.shields.io/badge/License-CC_BY_4.0-blue?style=flat-square)](../LICENSE)

## What Apex is

Apex AI Academy helps you and your agent learn AI together: every lesson has a Human view for you and an Agent view that teaches your agent how to support you, while you stay in charge. Lessons are drafted by AI agents, fact-checked against cited sources and audited by a human owner ([method](https://apexai.academy/about.html#method)).

## Free courses and lessons

Start with [AI Foundations for Humans and Working with AI Tools](https://apexai.academy/courses.html). Both courses contain free lessons alongside paid material; check each lesson’s access label. Practice the free lessons with our [activities](https://github.com/ApexAI-Academy/activities).

## Go deeper with Premium

**$10/month or $100/year.** Premium adds in-depth lessons, early access, earlier and subscriber-only news, and no ads. [See plans](https://apexai.academy/#plans) or [create an account](https://apexai.academy/account/). Public lessons and the public content API are free.

## For developers

Use the key-free [content API](https://apexai.academy/api/public/content), [agent reading guide](https://apexai.academy/llms.txt) and [runnable examples](https://github.com/ApexAI-Academy/sample-agents). Cache responses and poll news no more than once every five minutes. Cite original news sources and respect access labels.


## Connect your agent to Apex MCP

Apex runs a remote MCP server at `https://apexai.academy/mcp` (Streamable HTTP, protocol `2025-06-18`, stateless JSON; GET returns 405). Public tools need no key.

```json
{ "mcpServers": { "apex-ai-academy": { "type": "http", "url": "https://apexai.academy/mcp" } } }
```

Or test it with curl:

```sh
curl https://apexai.academy/mcp -H 'Content-Type: application/json' -H 'Accept: application/json, text/event-stream' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

Public tools: `list_courses`, `list_lessons`, `get_lesson` (view `agent` | `human` | `both`), `search`, `latest_news`, `get_pricing`, `subscribe_link`. Premium tools (`get_premium_lesson`, `get_progress`, `mark_lesson_complete`) need a personal key sent as `Authorization: Bearer <key>`. Docs: [developer hub](https://apexai.academy/developers/) · [server card](https://apexai.academy/.well-known/mcp.json) · [llms.txt](https://apexai.academy/llms.txt). Rate limit: 60 requests/minute per anonymous IP.

## One lesson, three views

Every lesson page has a Human / Agent / Both switch. The same switch is available in the API (`?view=`) and in MCP `get_lesson`.

| 🧑 Human | 🤖 Agent | Both |
| --- | --- | --- |
| ![Human view of "LLMs in plain words"](https://raw.githubusercontent.com/ApexAI-Academy/.github/main/assets/screenshots/view-human.png) | ![Agent view of "LLMs in plain words"](https://raw.githubusercontent.com/ApexAI-Academy/.github/main/assets/screenshots/view-agent.png) | ![Both view of "LLMs in plain words"](https://raw.githubusercontent.com/ApexAI-Academy/.github/main/assets/screenshots/view-both.png) |

_Screenshots of [LLMs in plain words](https://apexai.academy/lesson.html?id=1), captured from the live site on 2026-10-15._

## Repositories

| Repository | What you’ll find |
| --- | --- |
| [activities](https://github.com/ApexAI-Academy/activities) | Practical exercises for confirmed free lessons |
| [sample-agents](https://github.com/ApexAI-Academy/sample-agents) | Dependency-free public API examples in Node and Python |
| [awesome-agent-teaching](https://github.com/ApexAI-Academy/awesome-agent-teaching) | Resources for teaching humans AI |

[Visit Apex AI Academy](https://apexai.academy/) · Profile text and artwork: [CC BY 4.0](../LICENSE).
