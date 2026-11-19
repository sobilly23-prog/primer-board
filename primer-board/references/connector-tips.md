# Connector tips

Optional, tool-specific notes for opening the links on a context board. Connector and tool names vary between AI tools and MCP servers, so treat these as hints, not exact calls. PRIMER's main instructions work without this file.

## Figma

- `whoami` is the cheapest check that the connection works. It also shows the account's plans and seat, which tells you the rate limit (View and Collab seats, and Starter plans, get about 20 calls a month).
- "Can't access this file" usually means the signed-in account isn't on the plan that owns the board. Ask the designer to check which account their AI tool is using.
- `use_figma` runs plugin-API JavaScript. PRIMER's scripts are read-only. Never run one that creates, changes, or removes nodes on a context board.

## Atlassian (Confluence, Jira)

- Confluence page tools usually take a site id and a page id. Many connectors accept the site hostname (e.g. `acme.atlassian.net`) as the site id, and a short link (`/wiki/x/AbCdEf`) as the page id.
- For Jira issues, request the `comment`, `status`, and `priority` fields. Epic comments often hold sibling epics, architecture docs, and decisions that never reached the board.
- Some setups install more than one Atlassian connector with only one authorized. A warning about one says nothing about the other. Probe with a cheap call such as the current-user lookup.

## Google Drive (Docs, Slides, Sheets)

- File tools need the real file id. Take it from the URL (`/d/<fileId>/`).
- "Not found" usually means the file isn't shared with the signed-in account, not that it doesn't exist. Say which.

## Slack and Teams

- A link to one message is usually inside a thread. Read the whole thread, because the decision is often in a reply.
- Private channels are invisible unless the signed-in account is a member. List them under "Couldn't open".

## Notion, Linear, GitHub Issues, and others

- The same pattern applies: one cheap read call to confirm access, open every link from the board, and list what you couldn't open.
