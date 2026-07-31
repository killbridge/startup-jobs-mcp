# Startup Jobs MCP Server

Search live [startup.jobs](https://startup.jobs) listings from Claude, Cursor, ChatGPT, or any [Model Context Protocol](https://modelcontextprotocol.io) client.

**Docs:** https://startup.jobs/mcp  
**Endpoint (Streamable HTTP):** `https://api.startup.jobs/mcp`  
**Smithery:** https://smithery.ai/servers/jobs/startup-jobs  
**Official Registry:** `io.github.marckohlbrugge/startup-jobs-mcp`  


This repository is the public listing + registry package for the hosted MCP server. The server itself runs on startup.jobs (not in this repo).

## What you get

- Search startup jobs (keyword, role, country, remote / hybrid / on-site, employment type)
- Full job details and company profiles
- Hiring trends and salary benchmarks from listings that disclose pay
- Free anonymous access (recent listings); optional API key for attribution / full archive

## Connect

### Claude Code

```bash
claude mcp add --transport http startup-jobs https://api.startup.jobs/mcp
```

### Cursor

Add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "startup-jobs": {
      "url": "https://api.startup.jobs/mcp"
    }
  }
}
```

### Claude / ChatGPT

Paste `https://api.startup.jobs/mcp` as a custom connector. No authentication required for the free tier.

### Optional API key

Create a free key at https://startup.jobs/account/api_keys and send it as:

```http
Authorization: Bearer sj_...
```

or (for gateways that reserve `Authorization`):

```http
X-Api-Key: sj_...
```

## Tools

| Tool | Description |
| --- | --- |
| `search_jobs` | Search live listings with filters |
| `get_job` | Full job description + apply URL |
| `get_company` | Company profile and live listing count |
| `get_company_jobs` | All live listings for one company |
| `list_roles` | Role taxonomy for filters |
| `list_countries` | Countries with jobs |
| `job_trends` | Posting volume over time |
| `salary_benchmarks` | Salary percentiles from disclosed pay |

## Example prompts

- Find remote senior Rails jobs at startups posted this week
- What are Series B fintech companies hiring for in Europe?
- Salary percentiles for product designer roles in the US
- Show hiring trends for AI engineer roles over the last year

## Related

- REST API: https://startup.jobs/api
- Product: https://startup.jobs

## License

MIT — see [LICENSE](LICENSE). The job data remains © Killbridge / startup.jobs; this repo covers the MCP listing materials and registry metadata.
