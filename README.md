# HappyKeywords MCP server

App Store keyword research (ASO) from your AI agent. Ask Claude Code, Codex, Cursor, Claude or any
MCP app which keywords to target, where your app ranks in 50+ countries, and what to fix in your
listing.

The MCP server is built into **HappyKeywords**, a Mac app. This repo holds the setup and the tool
list only; there is no source code here. Docs: https://happykeywords.com/docs/mcp

## What it does

- Track your apps and competitors in 50+ countries, with daily ranks
- Estimated demand and difficulty for every keyword (0–100 estimates from App Store search results, not Apple's search counts)
- An Audit that scores your listing out of 100 and says what to fix first
- Write and localize name, subtitle and keyword options
- Upload them into your draft version in App Store Connect: a preview first, Undo after. Nothing is ever submitted for review.
- Hot niches and product ideas before you build

104 tools. Long jobs run inside the app; the agent follows them with `wait`.

## Requirements

- macOS 14 or later (Apple silicon or Intel)
- HappyKeywords in /Applications: download at https://happykeywords.com/?ref=github-mcp
- 7-day free trial, no card. Then a one-time license ($29 in Early Access). No subscription.
- Tools list without a license; tool calls need the trial or a license.

## Connect

One click: in HappyKeywords, open **Settings → AI apps (MCP)** and press **Add** next to your agent.

Or by hand:

**Claude Code**
```sh
claude mcp add-json --scope user happykeywords '{"type":"stdio","command":"/Applications/HappyKeywords.app/Contents/MacOS/HappyKeywords","args":["--mcp"]}'
```

**Codex**
```sh
codex mcp add happykeywords -- "/Applications/HappyKeywords.app/Contents/MacOS/HappyKeywords" --mcp
```

**Cursor, Claude desktop and other MCP apps** (`~/.cursor/mcp.json`, `claude_desktop_config.json`)
```json
{
  "mcpServers": {
    "happykeywords": {
      "command": "/Applications/HappyKeywords.app/Contents/MacOS/HappyKeywords",
      "args": ["--mcp"]
    }
  }
}
```

## Try asking

- Which of my apps lost ranks since the last check?
- Where is my app outside the top 10 in Germany, and what would it take to get in?
- Run the Audit for my app and tell me what to fix first.
- Write three name and subtitle options, then localize the best one into German and French.
- Find hot niches in the US App Store and show me product ideas for the best one.

## Tools

| Group | Tools |
|---|---|
| Apps, keywords and ranks | 41 |
| App Store Connect | 5 |
| AI and jobs | 17 |
| Audit | 4 |
| Optimize | 33 |
| Upload | 4 |

Full list with inputs: https://happykeywords.com/docs/mcp#tools

## Privacy

Everything runs on your Mac. App Store Connect keys stay in the macOS Keychain, and no MCP tool can
read them. Uploads happen only after you approve the preview.

## Support

https://happykeywords.com/contact
