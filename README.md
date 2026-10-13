<img src="logo-400.png" alt="PDF Samenvoegen logo" width="96" height="96">

# PDF Samenvoegen MCP server

**Merge your own PDFs in a confirmed order and get one downloadable PDF.**

Remote MCP server: `https://pdfsamenvoegen.nl/mcp` (Streamable HTTP) · Website: [pdfsamenvoegen.nl](https://pdfsamenvoegen.nl/)

## What it does

PDF Samenvoegen merges PDFs you uploaded to your account on pdfsamenvoegen.nl. The assistant lists your files with names and page counts, proposes a merge order, and after you confirm it produces one PDF with a download link that only opens in your signed-in browser.

Up to five files, 5 MB each, 25 MB in total. Files expire after forty minutes.

## Connect

- **Server URL:** `https://pdfsamenvoegen.nl/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Sign in with your pdfsamenvoegen.nl account.

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the server URL.

**Claude Code:**

```bash
claude mcp add --transport http pdfsamenvoegen https://pdfsamenvoegen.nl/mcp
```

**Cursor, VS Code, Cline, Windsurf and other clients** (`mcp.json` / `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "pdfsamenvoegen": {
      "type": "http",
      "url": "https://pdfsamenvoegen.nl/mcp"
    }
  }
}
```

Cline uses `"type": "streamableHttp"`; see [llms-install.md](llms-install.md).

## Tools

| Tool | What it does |
|---|---|
| `document_account / list_documents` | Account and uploaded files with page counts. |
| `prepare_merge` | Propose the merge order. |
| `merge_documents / get_merge` | Merge after confirmation; download link. |

## Example prompts

- Merge my invoice, the quote and the terms into one PDF, quote first.
- Which PDFs did I upload?
- Give me the link to the merged file.

## Links

- Website: https://pdfsamenvoegen.nl/
- Documentation: https://pdfsamenvoegen.nl/plugin/
- Privacy policy: https://pdfsamenvoegen.nl/plugin/privacy/
- Terms: https://pdfsamenvoegen.nl/voorwaarden/
- Support: mailto:support@pdfsamenvoegen.nl

## Keywords

merge PDF, combine PDF files, PDF tool, join PDFs, document merge.

Nederlands: PDF samenvoegen, PDF bestanden samenvoegen, PDF combineren, pdf's samenvoegen gratis, documenten samenvoegen.

## More MCP servers by Samautomation

- [Scamchecker.nl](https://scamchecker.nl/): Check a suspicious email, SMS, WhatsApp message or link for scam signals (Netherlands, Belgium). ([listing](https://github.com/smrht/scamchecker-mcp))
- [Klussenbeheer](https://samdesk.nl/klussenbeheer/): Job management for Dutch service companies: jobs, customers, planning, quotes and invoices. ([listing](https://github.com/smrht/klussenbeheer-mcp))
- [Muziek maken met AI](https://muziekmakenmetai.nl/): Make an original song from a prompt or your own lyrics. Two versions per song, MP3 download. ([listing](https://github.com/smrht/muziekmakenmetai-mcp))
- [Beheer je WP](https://beheerjewp.nl/): Manage a WordPress site from your AI assistant: read, search, propose edits, Search Console data. ([listing](https://github.com/beheerjewp/beheerjewp-mcp))
- [UlazAI Media](https://ulazai.com/): Create private AI images with your UlazAI account: pick a model, confirm, generate, download. ([listing](https://github.com/ulazai/ulazai-mcp))
- [Backlinkswinkel](https://backlinkswinkel.nl/): Search Dutch websites for backlinks, check metrics and prices, order after confirmation, track. ([listing](https://github.com/backlinkswinkel/backlinkswinkel-mcp))
- [Backlinksbeheer](https://backlinksbeheer.nl/): Read your stored backlinks, link checks and lost-link alerts per domain. Read-only. ([listing](https://github.com/smrht/backlinksbeheer-mcp))
- [Samautomation Video](https://samautomation.work/): Render an MP4 from your own images, clips, voice-over and timed captions. JSON to video. ([listing](https://github.com/smrht/samautomation-video-mcp))
- [Diamond Painting Converter](https://diamondpaintingconverter.com/): Find your purchased diamond painting patterns and download the PDF with DMC colour legend. ([listing](https://github.com/smrht/diamondpaintingconverter-mcp))
- [Nummerschilderen.com shop advisor](https://nummerschilderen.com/): Search paint-by-number kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/nummerschilderen-mcp))
- [DiamondPaintingWinkel.nl shop advisor](https://diamondpaintingwinkel.nl/): Search diamond painting kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/diamondpaintingwinkel-mcp))
- [AI Rechtshulp](https://ai-rechtshulp.nl/): Search Dutch and EU case law with ECLI sources and verify quotes against the judgment. ([listing](https://github.com/smrht/ai-rechtshulp-mcp))
- [SamDesk Support](https://samdesk.nl/support/plugin/): Read your SamDesk support inbox, find customer agreements and draft replies. Read-only. ([listing](https://github.com/smrht/samdesk-support-mcp))

## Publisher

Samautomation, Wognum, the Netherlands · https://samautomation.work

This repository holds the public listing (README, `server.json`, install notes). The server itself is hosted by the publisher; there is nothing to install or build.
