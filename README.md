# GFIN Funding Radar plugin

A hosted MCP server that searches public funding opportunities from Go Fund It Now and returns the
funder, the stated amount, the deadline or an explicit unknown, and the funder's own page.

- Endpoint: `https://app.gofunditnow.com/api/mcp` (Streamable HTTP, no authentication)
- Tools: `search_opportunities`, `get_opportunity`
- Docs: https://app.gofunditnow.com/developers/mcp
- Usage guide: https://app.gofunditnow.com/developers/mcp/guide

## Authentication

None for the public catalogue. No credentials belong in these files.

## What it covers

The public funding catalogue: opportunities from funders' own published pages. It does not offer an
organization's private matches, saved items, pipeline or requirement checks; those live in the GFIN
product at https://app.gofunditnow.com and are not exposed to any AI host.

## Test

Install the plugin, select the `gfin` server, then ask a bot: "Find funding opportunities in Georgia
for a nonprofit." It should call `search_opportunities` and return rows with a title, funder,
deadline and the funder's link. A deadline the source does not state is returned as unknown.
