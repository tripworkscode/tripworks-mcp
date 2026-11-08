# TripWorks MCP Server

[![TripWorks Tour and Activity Booking MCP connector – tool definition quality and endpoint health on Glama](https://glama.ai/mcp/connectors/com.tripworks/tripworks/badges/score.svg)](https://glama.ai/mcp/connectors/com.tripworks/tripworks)

Ask your AI assistant about your tours, activities and attractions, and let it make changes for you, in plain English. The TripWorks MCP server connects Claude, ChatGPT, Gemini and other [Model Context Protocol](https://modelcontextprotocol.io) clients to your live [TripWorks](https://www.tripworks.com) booking account.

- **Remote server, nothing to install.** Streamable HTTP at `https://mcp.tripworks.com/mcp`
- **Sign in as yourself.** OAuth 2.1 with PKCE and dynamic client registration. No API keys to paste.
- **Runs with your permissions.** The assistant can see and do only what your TripWorks permission group allows.
- **Preview before it changes anything.** Every create, edit and delete shows a preview and waits for your confirmation.

Official MCP Registry: `com.tripworks/tripworks` · [registry listing](https://registry.modelcontextprotocol.io/?q=com.tripworks%2Ftripworks)

## Connect

Server URL (the same for every account):

```
https://mcp.tripworks.com/mcp
```

1. In TripWorks, open **Setup > Integrations > AI Assistants** and switch on **Enable AI assistants**.
2. Add the URL to your assistant (below).
3. Sign in, choose the account, choose **Read** and/or **Write** access, and approve.

### Claude

Claude.ai and Claude Desktop: Settings > Connectors > Add custom connector, paste the URL. Step-by-step: [Connect Claude to TripWorks](https://help.tripworks.com/connect-ai-assistants/claude-connector-for-tripworks).

Claude Code:

```bash
claude mcp add --transport http tripworks https://mcp.tripworks.com/mcp
```

### ChatGPT and Gemini

Add a custom connector (ChatGPT) or custom app (Gemini) and paste the URL. Step-by-step guides:
[ChatGPT](https://help.tripworks.com/connect-ai-assistants/chatgpt-connector-for-tripworks) ·
[Gemini](https://help.tripworks.com/connect-ai-assistants/gemini-connector-for-tripworks) ·
[Google Antigravity](https://help.tripworks.com/connect-ai-assistants/antigravity-connector-for-tripworks)

### Any other MCP client

Use the URL above as a remote streamable-HTTP server. OAuth discovery is published at
`https://mcp.tripworks.com/.well-known/oauth-authorization-server`.

Full setup guide: [Connect TripWorks to your AI assistant](https://help.tripworks.com/connect-ai-assistants/connect-tripworks-mcp-to-your-ai-assistant)

## Example commands

Once connected, try:

**Front desk**
- "Who's booked on tomorrow's 10:00 AM departure? Show check-in and waiver status."
- "Find the booking for confirmation code 4F7K2."
- "Find guests named Rivera and show their contact details."
- "Check in the Nguyen party and mark their waivers signed."

**Reports and insights**
- "How many guests have we added this month, compared with last month?"
- "Run a sales report for last month and give me the download link."
- "What are callers asking about most this week?"

**Catalog and setup**
- "List every experience at our downtown location."
- "Add a new location called Riverside Kayak Launch."
- "Which of our kayak tours have a group minimum?"

**Guests and team**
- "Find customers with a gmail address."
- "Update this customer's email address."
- "Who changed the timed-entry experience yesterday?"

Every change starts as a preview. Nothing is saved until you confirm.

## What it can do

| Area | Capabilities |
| --- | --- |
| Trips and bookings | Look up trips, orders, guests, products, add-ons, waivers and custom fields. Check guests in, change status, mark waivers signed, add or remove guests |
| Trip notes | Read and add notes |
| Day-of manifest | Who is booked on each departure, with check-in and waiver status |
| Reports and analytics | Run reports with a download link. Counts, totals, averages and period comparisons |
| Experiences, locations, customers | Look up, create, edit and (where allowed) delete |
| Booking restrictions, resources | Manage restrictions, assign resources to departures, create and clear blackouts |
| Resellers, promo codes, trip sources, team members | Look up and review. Edit resellers |
| Reviews and phone calls | Guest reviews. Calls with summaries, transcripts, questions and tips |
| Audit log and account settings | What changed, when and by whom. Settings and guest policies |
| Search | Trips, bookings, customers, gift cards, payments, resellers, calls, notes, voucher codes |

New tools are added regularly.

## Security

- You approve each connection by signing in to TripWorks in your browser. No password or key is shared with the assistant.
- Two layers of control: your permission group, and the Read / Write choice you make when approving.
- One connection reaches one account.
- Turning off **Enable AI assistants** disconnects every assistant at once.
- Anything the assistant reads is passed to that AI platform under its own terms.

## Building software instead?

For your own integrations use the [TripWorks REST API](https://api-docs.tripworks.com) ([OpenAPI spec](https://api-docs.tripworks.com/openapi.json)). MCP is for a person talking to an assistant; the REST API is for software. Not sure which fits? See [Does TripWorks have an API?](https://help.tripworks.com/api-and-integrations/does-tripworks-have-an-api)

## Links

- [TripWorks](https://www.tripworks.com), tour and activity booking software · [Book a demo](https://www.tripworks.com/book-a-demo)
- [Help center](https://help.tripworks.com) · [MCP setup guide](https://help.tripworks.com/connect-ai-assistants/connect-tripworks-mcp-to-your-ai-assistant)
- [REST API docs](https://api-docs.tripworks.com) · [OpenAPI spec](https://api-docs.tripworks.com/openapi.json) · [llms.txt](https://www.tripworks.com/llms.txt)
- [Official MCP Registry listing](https://registry.modelcontextprotocol.io/?q=com.tripworks%2Ftripworks)
- [Support](mailto:support@tripworks.com)
