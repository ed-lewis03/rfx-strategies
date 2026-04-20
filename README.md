# rfx-strategies

RFx agent strategy prompts consumed by `rfx-ace` (http://rfx-ace:8080).

## Files
- `rfx.chat.md` — chat / Q&A about a solicitation
- `rfx.strategize.md` — per-requirement capture strategy
- `rfx.draft.md` — proposal response writing

## How it's loaded
`rfx-ace` fetches `https://raw.githubusercontent.com/ed-lewis03/rfx-strategies/{ref}/{tag}.md` at call time. If the fetch fails (no network / missing tag and no `strategy_ref` pin), falls back to a baked-in copy in the container.

Pin a specific ref per call via `strategy_ref` in the request body; no local fallback applies when a ref is explicitly pinned (explicit-fail semantics).
