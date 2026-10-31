# SEO, AEO and GEO bot

A Claude Code plugin that keeps working on search visibility for **Sapphire Botanics** (sapphirebotanics.com). It aims to rank in Google and Bing and to get cited by AI assistants: Google AI Overviews, ChatGPT, Perplexity, Gemini, Claude and Copilot.

## What's inside

| Skill | Source | Job |
|---|---|---|
| **seo-ops** | this repo | Runs the bot: audit, work and report modes, the approval flow, and the safety rules |
| seo-audit | coreyhaines31/marketingskills | Technical and on-page audit |
| ai-seo | coreyhaines31/marketingskills | GEO/AEO: citations in AI answers |
| schema | coreyhaines31/marketingskills | JSON-LD structured data |
| content-strategy | coreyhaines31/marketingskills | Topic clusters and pillar content |
| site-architecture | coreyhaines31/marketingskills | Hierarchy, URLs, internal links |
| programmatic-seo | coreyhaines31/marketingskills | Template pages at scale |
| link-building | coreyhaines31/marketingskills | Links and brand mentions |
| seo-ecommerce | agricidaniel/claude-seo | Product pages and product schema |
| core-web-vitals | addyosmani/web-quality-skills | LCP, INP and CLS fixes |
| performance | addyosmani/web-quality-skills | Supporting reference for core-web-vitals (measurement, RUM) |

The nine playbooks are copied unmodified from these upstream commits. Each one passed NVIDIA SkillSpector (SAFE) before it was added.

- coreyhaines31/marketingskills `820ad2c1c0ac4cc350158bd7912c753681a7d173`
- agricidaniel/claude-seo `6be93f45064ffbadced572b5d5c95f55fd263af0`
- addyosmani/web-quality-skills `afa8da942115f2961fdbfa80807ea0b232ff6c00`

`skills/seo-ops/brand-context.md` holds Sapphire's positioning, products, customer, voice rules and starting keyword ideas. Keep this repo private.

## Install in Claude Code

```
/plugin marketplace add aiarrchith/seo-geo-aeo-bot
/plugin install seo-geo-aeo-bot@aiarrchith-seo
```

Then ask: `run seo-ops in audit mode`.

For the best results in Claude Code, also add these MCP servers so the bot measures instead of estimating:
- **Search Console:** [AminForou/mcp-gsc](https://github.com/AminForou/mcp-gsc) gives real queries, clicks and indexing.
- **Chrome DevTools:** [ChromeDevTools/chrome-devtools-mcp](https://github.com/ChromeDevTools/chrome-devtools-mcp) gives real Core Web Vitals traces. Run it with `--isolated --no-usage-statistics`.
- **Shopify:** the Shopify connector, which the bot uses to read the store and publish approved changes.

## How it works

- **Monday · audit:** inventories the store, checks AI answers for 20 tracked customer questions, scores the week and refills the work queue.
- **Wednesday and Friday · work:** publishes what you approved, then drafts the next five items for review.
- **1st of the month · report:** what shipped, what moved, and next month's priorities.

State lives in the Sapphire Search Desk, a private claude.ai artifact with a database. Nothing goes live in the store until it's approved there. The bot never edits theme code, deletes anything, creates redirects, changes prices or sends messages.

## Updating the playbooks

Don't pull upstream changes blindly. To move to a newer upstream commit:
1. Re-run SkillSpector on the new version.
2. Copy the folders over.
3. Update the commit hashes here and in `skills/seo-ops/SKILL.md`.

## Licenses

The playbooks are MIT licensed by their authors. See `licenses/` and `THIRD_PARTY_NOTICES.md`.
