# Caisey MCP

This repository holds listing metadata for the hosted Caisey MCP server. The server itself is hosted at https://helpforsupport.com/mcp; source is not published here.

Endpoint: `https://helpforsupport.com/mcp` (Streamable HTTP, OAuth 2.1)

Work with the Caisey workspace you sign in to from Claude, ChatGPT, Cursor, VS Code, or any MCP client that supports remote servers with OAuth. List enrolled PCs, read troubleshooting chats, send a prompt to a PC, and answer pending approvals and questions.

Commands still go through Caisey's approval policy and risk analysis. MCP does not bypass them. Every action is recorded in the audit log with origin `mcp` and the OAuth client name.

### Connect

**Claude Code**
```bash
claude mcp add --transport http caisey https://helpforsupport.com/mcp
```

**Cursor / VS Code (`mcp.json`)**
```json
{ "mcpServers": { "caisey": { "url": "https://helpforsupport.com/mcp" } } }
```

**Claude.ai / ChatGPT:** add `https://helpforsupport.com/mcp` as a custom connector.

On first use your client opens a browser. Sign in to Caisey, pick a workspace, and accept the terms. No API key. Revoke access any time in Settings > Remote MCP.

### Tools (14)
| Tool | What it does |
| --- | --- |
| list_devices / get_device | List or load PCs in your workspace |
| list_sessions / read_transcript | List or read Caisey chats |
| send_prompt | Send a prompt to a PC (runs under the approval policy) |
| get_session_status / get_session_live / watch_session / wait_for_messages | Follow a running chat |
| list_pending_approvals / respond_to_approval | See and answer command approvals |
| list_pending_questions / answer_question | See and answer operator questions |
| list_org_pending | Pending approvals and questions across the workspace |

### Pricing
Free ($0, 1 personal device), Basic ($5/mo), Family IT ($10/mo), Business ($20 per technician/mo). 30-day trial. Details at https://helpforsupport.com

### Links
- Docs: https://helpforsupport.com/docs/remote-mcp
- Privacy: https://helpforsupport.com/privacy
- Terms: https://helpforsupport.com/terms
- Contact: judah@zelek.tech

Caisey is in beta. Published by Zelek Tech. Also listed in the official MCP Registry as `com.helpforsupport/caisey`.

### License
The files in this repository (docs and listing metadata) are MIT licensed. The Caisey service itself is proprietary and is not covered by this license.
