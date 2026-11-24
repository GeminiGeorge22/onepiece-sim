# One Piece Sim

[![onepiece-sim MCP connector](https://glama.ai/mcp/connectors/io.github.GeminiGeorge22/onepiece-sim/badges/score.svg)](https://glama.ai/mcp/connectors/io.github.GeminiGeorge22/onepiece-sim)

One Piece Sim is a **One Piece Card Game simulator** you add to Claude, ChatGPT, Cursor, or VS Code. Paste a deck and ask: Is this a legal Leader + 50 list? How often is this card stuck in Life? Goldfish this list.

Operated by **FMF Tools**.

- Live site: https://onepiece-sim.fmf-x402.workers.dev/
- MCP endpoint (Streamable HTTP): https://onepiece-sim.fmf-x402.workers.dev/mcp
- Install page: https://onepiece-sim.fmf-x402.workers.dev/install
- Tools and prices: https://onepiece-sim.fmf-x402.workers.dev/docs

No account is required. `tools/list`, deck check, and opening-hand odds are free. Paid sims are charged per successful call through MPP on Tempo or x402 on Base (USDC). Bad input is refused and is not charged.

## Install

MCP server URL: `https://onepiece-sim.fmf-x402.workers.dev/mcp`

### Claude Desktop

Settings → Connectors → Add custom connector → URL: `https://onepiece-sim.fmf-x402.workers.dev/mcp`

Or add this to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "onepiece-sim": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://onepiece-sim.fmf-x402.workers.dev/mcp"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add --transport http onepiece-sim https://onepiece-sim.fmf-x402.workers.dev/mcp
```

### Cursor

`~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):

```json
{
  "mcpServers": {
    "onepiece-sim": {
      "url": "https://onepiece-sim.fmf-x402.workers.dev/mcp"
    }
  }
}
```

### VS Code (Copilot agent mode)

```bash
code --add-mcp '{"name":"onepiece-sim","type":"http","url":"https://onepiece-sim.fmf-x402.workers.dev/mcp"}'
```

### ChatGPT

Settings → Apps & Connectors → Advanced settings → turn on Developer mode → Create connector. Name: One Piece Sim. MCP server URL: `https://onepiece-sim.fmf-x402.workers.dev/mcp`. Authentication: none.

## Tools

| MCP tool | Price |
|---|---|
| onepiece_deck_check | free |
| onepiece_opening_hand_odds | free |
| onepiece_draw_odds | $0.001 |
| onepiece_life_odds | $0.001 |
| onepiece_goldfish | $0.003 |

## Licence and fan notice

This repository is MIT licensed. One Piece Sim is an unofficial fan tool, not affiliated with or endorsed by Bandai, Toei, or Eiichiro Oda. ONE PIECE and card names are trademarks of their owners. Card data comes from the OPTCG API. Card data tools are free. Paid tools sell only our own computation and return no card data.

Contact: fmf-tools@agentmail.to
