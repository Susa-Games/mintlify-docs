> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

## Terminology

{/* Add product-specific terms and preferred usage */}
{/* Example: Use "workspace" not "project", "member" not "user" */}

## Style preferences

{/* Add any project-specific style rules below */}

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references

## Content boundaries

This site is public. The audience is **game developers outside the company** — not SusaPlay
staff. Before adding a page, ask whether an external developer needs it to integrate. If not,
it belongs in the private `susaplay_backend` repo under `docs/`.

Mintlify builds and serves **every** `.mdx` file in this repo. A page left out of `docs.json`
navigation is still reachable at its URL, so removing a page from the nav does not make it
private — the file has to be deleted.

Do not document here:

| Topic | Where it lives instead |
| --- | --- |
| Firebase project ids, regions, per-function memory/timeout, Cloudflare config | `docs/INFRASTRUCTURE.md` |
| Internal system design and module boundaries | `docs/ARCHITECTURE.md` |
| Firestore collection schemas — developers use the API, never Firestore directly | `docs/DATA_MODEL.md` |
| Security-rule internals, claim structure, admin auth | `docs/SECURITY.md` |
| Admin panel and operations workflows | `docs/liveops/LIVEOPS_GUIDE.md` |
| BigQuery datasets, views, analytics pipeline | `docs/BIGQUERY_VIEWS.md` |

## Accuracy

Every API name, event name, method signature, and version number must be verified against the
source in `susaplay_backend` or `com.susaplay.sdk` before publishing. Documenting a planned
feature as if it shipped is worse than omitting it — developers build against it and lose hours.

Example of what to avoid: `sdk/analytics.mdx` listed four events as "tracked automatically by
the SDK". Only one of them existed. Three were never implemented.

When a behaviour depends on an SDK version, state the version.
