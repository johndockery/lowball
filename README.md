# lowball

A Claude Code skill that generates realistic lowball offers for home listings.

Paste a Zillow/Redfin URL and it'll open the listing in Chrome, find every flaw, estimate repair costs, and draft a polite-but-devastating offer message 15-35% below asking.

## Usage

```
/lowball https://www.zillow.com/homedetails/...
```

## Requirements

- [Claude Code](https://claude.com/claude-code)
- Chrome DevTools MCP server (for reading listings)

## Install

Clone this repo and open it in Claude Code:

```bash
git clone https://github.com/johndockery/lowball.git
cd lowball
claude
```

Then use `/lowball` with any listing URL.
