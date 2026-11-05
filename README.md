# VirtualSpace Agent Skills

Use your own AI agent with VirtualSpace Projects, Chat, Calendar, and Notes. Each skill is a folder with a portable `SKILL.md`.

| Skill | Use it to |
| --- | --- |
| [VirtualSpace Projects](skills/virtualspace-projects/SKILL.md) | Review a board section, read a task and its discussion, or draft and post updates |
| [VirtualSpace Chat](skills/virtualspace-chat/SKILL.md) | Catch up on a channel, find a decision, or ask a follow-up question |
| [VirtualSpace Calendar](skills/virtualspace-calendar/SKILL.md) | Review visible events, propose meeting times, or create an event on request |
| [VirtualSpace Notes](skills/virtualspace-notes/SKILL.md) | Find notes, capture decisions, or share a note with a specified audience |
| [VirtualSpace Daily Task Run](skills/virtualspace-daily-task-run/SKILL.md) | Evaluate and work on one eligible task from configured projects |

## Connect and install

1. Open the AI Agents App in your VirtualSpace workspace and copy the MCP server URL. Add it as a remote HTTP MCP server in your client. Complete OAuth and select the intended workspace.
2. Download the skill folders from this repository. Copy each entire folder to the directory your client scans, or use the instructions in `SKILL.md` as a prompt if your client has no skill loader.
3. Try a read first. For example, ask the agent to find a project and list one of its sections. Use a test project to verify any write.

| Client | Skill location | MCP setup |
| --- | --- | --- |
| Codex | `~/.agents/skills/` | [Codex MCP guide](https://developers.openai.com/codex/mcp) |
| Claude Code | `~/.claude/skills/` | [Claude Code MCP guide](https://code.claude.com/docs/en/mcp) |
| Grok Build | `~/.grok/skills/` | [Grok Build skills and MCP packaging](https://docs.x.ai/build/features/skills-plugins-marketplaces) |
| Grok web | Use the skill text as a prompt | [Grok custom connectors](https://docs.x.ai/grok/connectors) |

Client verification is pending. A client must support the VirtualSpace OAuth connection and the tools a workflow calls. Scheduled code changes also require a runtime with repository and test access.

## Configure a daily run

Copy the [example configuration](examples/daily-task-run.yml) to a location your agent can read. Replace the fictional mappings with the projects and repositories you want the run to use. Start in report mode and verify the selected scope. Schedule the skill in your agent runtime if it supports scheduled work. Choose the handoff and enable individual writes only after testing that configuration.

## Troubleshooting

- If tools are missing or access is denied, check the selected workspace, enabled scopes, and your access to the resource in VirtualSpace.
- If a cursor fails, retry once with the same filters. Report an incomplete list if continuation still fails. Keyword search cannot replace a complete section listing.
- Calendar event visibility is limited to the connection. Treat meeting suggestions as tentative unless attendee availability was confirmed through an authorized source.

Released under the [MIT License](LICENSE).
