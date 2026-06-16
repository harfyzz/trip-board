# 🧵 Trip Board

A detective-style travel map. Lay out a holiday as an investigation board: a
central **stay** card (Airbnb/hotel) surrounded by the **places you visited**,
all connected back to home base with red string.

**Live:** https://harfyzz.github.io/trip-board/

## Features

- Central stay card (photo, name, address, price/night) with surrounding
  location cards (photo, address, price).
- Red strings connecting every spot to the stay, with **spring physics** — they
  lag, swing, and wiggle as you drag cards, then settle.
- **Taut ⟷ slack** slider to control how much the strings droop.
- Drag cards to rearrange, drag the board to pan, scroll to zoom.
- **🎲 New random trip** regenerates a fresh case file.

> First draft: locations are randomly generated and images are placeholders from
> [picsum.photos](https://picsum.photos) (loaded at runtime, so internet is
> needed for images).

## Running locally

It's a single static file — just open `index.html` in a browser. No build step.

## Deploying

Hosted on **GitHub Pages** from the `main` branch root. To update:

```sh
git add -A
git commit -m "your message"
git push
```

Pages rebuilds automatically within a minute or so.

## Design workflow (Figma)

This project is set up to build components to spec from Figma via the
**Figma Dev Mode MCP server**:

1. Open the **Figma desktop app** and enable the local MCP server
   (Preferences → *Enable Dev Mode MCP Server*). It serves on
   `http://127.0.0.1:3845`.
2. The server is registered with Claude Code at **local scope** (stored in
   `~/.claude.json`, not committed here):
   `claude mcp add --transport http --scope local figma http://127.0.0.1:3845/mcp`
3. Keep the Figma desktop app open (the server stops when Figma quits), select
   the frame/component to build, and ask Claude to build it.

## Tech

Plain HTML/CSS/JS, no dependencies. Fonts: Inter (UI), Caveat (handwritten card
titles), Special Elite (typewriter metadata).
