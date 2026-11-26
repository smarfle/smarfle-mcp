# Smarfle MCP server

The official remote MCP server for [Smarfle](https://www.smarfle.com), field service software for home service businesses such as pest control, cleaning, HVAC, plumbing and lawn care companies.

Connect Smarfle to Claude, ChatGPT or any assistant that supports remote MCP servers, then ask about your business in plain words: today's jobs, a customer's history, unpaid invoices. The assistant can also add a customer, update one, add a note or send a job request to your office.

- **Server URL:** `https://www.smarfle.com/api/mcp` (Streamable HTTP)
- **Sign-in:** OAuth 2.0 with dynamic client registration and PKCE. The owner or a manager of a Smarfle business signs in and approves each connection. A Smarfle API key also works as a bearer token.
- **Hosted by Smarfle.** Nothing to install or run.

## Set up

- **ChatGPT:** install the [Smarfle plugin](https://chatgpt.com/plugins/plugin_asdk_app_6b01d64c7fa481919c1a9b8e2314ec80). Guide: [smarfle.com/docs/chatgpt](https://www.smarfle.com/docs/chatgpt)
- **Claude:** add a custom connector with the server URL above. Guide: [smarfle.com/docs/claude](https://www.smarfle.com/docs/claude)
- **Other MCP clients:** add `https://www.smarfle.com/api/mcp` as a remote server and complete the sign-in in your browser.

Example config for clients that read an `mcpServers` file:

```json
{
  "mcpServers": {
    "smarfle": {
      "url": "https://www.smarfle.com/api/mcp"
    }
  }
}
```

## Tools

| Tool | What it does |
|---|---|
| `get_business` | The connected business: name, time zone and today's date there |
| `list_jobs` | Jobs for a day or date range, by status or customer |
| `get_job` | One job with customer, service, schedule, address, status and price |
| `find_customers` | Search customers by name, email, phone or company |
| `get_customer` | One customer with contact details, address, status and tags |
| `list_invoices` | Invoices by status (sent or overdue = unpaid), customer or job |
| `get_invoice` | One invoice with line items, totals, due date and payment status |
| `list_services` | The services the business offers, with prices |
| `create_customer` | Add a customer or lead |
| `update_customer` | Change a customer's contact details, address, status or notes |
| `request_job` | Send a job request to the office, which confirms and schedules it (nothing is sent to the customer) |
| `add_note` | Add a private note to a customer or job |

Every request is scoped to the one business that approved the connection. Reading is free. Changes count as API writes on the business's Smarfle plan.

## Links

- Smarfle: https://www.smarfle.com
- AI assistants feature page: https://www.smarfle.com/features/ai-assistants
- REST API docs: https://www.smarfle.com/docs/api
- All setup guides: https://www.smarfle.com/docs
- Privacy: https://www.smarfle.com/privacy
- Official MCP Registry entry: `com.smarfle/smarfle`

Questions: [contact Smarfle](https://www.smarfle.com/contact).
