# Calendly MCP Server

> Fork of [meAmitPatil/calendly-mcp-server](https://github.com/meAmitPatil/calendly-mcp-server) with Scheduling API integration and OAuth 2.0 support.

A Model Context Protocol (MCP) server for the Calendly API. Manage events, invitees, and schedule meetings directly via AI assistants.

## Installation

### Claude Desktop

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "calendly": {
      "command": "npx",
      "args": ["-y", "calendly-mcp-server"],
      "env": {
        "CALENDLY_API_KEY": "your_personal_access_token_here"
      }
    }
  }
}
```

### Cursor

Add to your Cursor MCP settings:

```json
{
  "mcpServers": {
    "calendly": {
      "command": "npx",
      "args": ["-y", "calendly-mcp-server"],
      "env": {
        "CALENDLY_API_KEY": "your_personal_access_token_here"
      }
    }
  }
}
```

## Configuration

| Variable | Required | Description |
|----------|----------|-------------|
| `CALENDLY_API_KEY` | Yes* | Personal Access Token ([get one here](https://calendly.com/integrations)) |
| `CALENDLY_CLIENT_ID` | Yes* | OAuth 2.0 client ID (alternative to PAT) |
| `CALENDLY_CLIENT_SECRET` | Yes* | OAuth 2.0 client secret |
| `CALENDLY_ACCESS_TOKEN` | No | OAuth access token (if already obtained) |
| `CALENDLY_REFRESH_TOKEN` | No | OAuth refresh token |
| `CALENDLY_USER_URI` | No | User URI for automatic defaults |
| `CALENDLY_ORGANIZATION_URI` | No | Organization URI for automatic defaults |

*Either `CALENDLY_API_KEY` or OAuth credentials (`CALENDLY_CLIENT_ID` + `CALENDLY_CLIENT_SECRET`) are required.

## Tools (12)

### OAuth

| Tool | Description |
|------|-------------|
| `get_oauth_url` | Generate OAuth authorization URL |
| `exchange_code_for_tokens` | Exchange authorization code for tokens |
| `refresh_access_token` | Refresh an expired access token |

### API

| Tool | Description |
|------|-------------|
| `get_current_user` | Get authenticated user info |
| `list_events` | List scheduled events with filtering |
| `get_event` | Get event details |
| `list_event_invitees` | List invitees for an event |
| `cancel_event` | Cancel a scheduled event |
| `list_organization_memberships` | List organization memberships |

### Scheduling API

| Tool | Description |
|------|-------------|
| `list_event_types` | List available event types |
| `get_event_type_availability` | Check available time slots |
| `schedule_event` | Book a meeting (requires paid Calendly plan) |

## API Limitations

- **Scheduling API** requires a paid Calendly plan (Standard or higher)
- Event rescheduling is not supported via API (only cancellation)
- Event type creation is not available via API
- Standard Calendly API rate limits apply

## Contributing

Pull requests welcome. See the [upstream project](https://github.com/meAmitPatil/calendly-mcp-server) for the original implementation.

## License

MIT License. See [LICENSE](LICENSE) for details.

## Credits

- Original implementation by [Amit Patil](https://github.com/meAmitPatil)
- Fork maintained by [84em.io](https://84em.io)
