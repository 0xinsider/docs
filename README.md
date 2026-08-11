# 0xinsider API Documentation

Docs for the [0xinsider API](https://docs.0xinsider.com): prediction-market data for agents, bots, and research tools.

## What is 0xinsider?

0xinsider provides trader grades, whale trades, smart-money flow, positions, and insider signals across Polymarket and Kalshi.

## API endpoints

- **Trader** — grades, P&L, win rate, and strategy
- **Leaderboard** — traders ranked by score
- **Whale Trades** — large trades with grade and category filters
- **Explore Markets** — whale-active markets by category, platform, and status
- **Market Intel** — smart-money flow and top positions
- **Search Markets** — markets by keyword and filters
- **Insider Radar** — unusual timing and accumulation patterns

## MCP Server

Connect AI agents to 0xinsider via the Model Context Protocol:

```bash
npx -y @0xinsider/mcp init
```

Supports Claude Code, Cursor, Codex, Gemini CLI, and other stdio-compatible MCP clients.

See the [MCP docs](https://docs.0xinsider.com/mcp) and the [npm package](https://www.npmjs.com/package/@0xinsider/mcp) for setup details.

## Local development

Install [Mintlify CLI](https://www.npmjs.com/package/mint):

```bash
npm i -g mint
```

Preview locally:

```bash
mint dev
```

Open `http://localhost:3000`.

Check that every OpenAPI operation has a Mintlify endpoint page and navigation
entry:

```bash
python3 scripts/check-openapi-parity.py
```

The docs OpenAPI spec (`api-reference/openapi.json`) is a synced copy of the
app's canonical spec (`web/public/api/v1/openapi.json` in the 0xinsider repo),
which is the single source of truth. After re-syncing it, confirm the two specs
are structurally identical (run from a sibling checkout, or adjust the path):

```bash
cp ../0xinsider/web/public/api/v1/openapi.json api-reference/openapi.json
python3 scripts/generate-objects-reference.py
python3 scripts/check-spec-sync.py --app-spec ../0xinsider/web/public/api/v1/openapi.json
python3 scripts/check-openapi-parity.py
```

## Links

- [API docs](https://docs.0xinsider.com)
- [API changelog](https://docs.0xinsider.com/changelog)
- [Terminal](https://0xinsider.com)
- [Product changelog](https://0xinsider.com/changelog)
- [Support](mailto:support@0xinsider.com)
