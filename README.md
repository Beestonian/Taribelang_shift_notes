# Taribelang shift notes — branching scenarios

Branching scenarios for the shift-notes learning module. Built with Switchback;
delivered as a single page and embedded in Articulate Rise 360 via an iframe.

## Layout

| Path | What it is |
|---|---|
| `index.html` | The player. One copy, shared by every scenario. Don't hand-edit. |
| `scenarios/default.json` | Loaded when no scenario is named. Currently *Why the shift ran late*. |
| `scenarios/<name>.json` | Loaded by `?s=<name>`. |

`index.html` fetches its scenario at load with a timestamp query, so no cache can
stale it. If a **named** scenario is missing it says so on screen rather than
quietly showing a different one. Opened from disk, it falls back to a copy baked
into the page.

## Adding a scenario

Drop `scenarios/lunch.json` in the folder. It is live at `?s=lunch` immediately;
no change to `index.html`. Names are limited to letters, digits, `-` and `_`.

## URLs

| Purpose | Address |
|---|---|
| Rise embed (default) | `https://beestonian.github.io/Taribelang_shift_notes/` |
| Rise embed (named) | `https://beestonian.github.io/Taribelang_shift_notes/?s=lunch` |
| Author the default | `.../?edit` |
| Author a named one | `.../?s=lunch&edit` |

## Editing

**Wording:** edit the JSON here on GitHub and commit. Pages redeploys in about a
minute; the Rise embed picks it up on next load.

**Structure:** open the authoring URL above. Rearrange on the canvas, then
Export, "Copy JSON only", and paste over the scenario file.

If a banner says "Restored the draft saved in this browser", click **Discard and
reload published** first, or you are editing a stale local draft.

## The lock

Each scenario carries `"locked": true`, which hides the **Build** button from
learners. `?edit` still works for authors. Keep the flag when pasting new JSON.

## Theming

Rise's CSS cannot cross the iframe boundary. Match it from inside the scenario
JSON instead: `style` accepts `bg`, `surface`, `ink`, `ink-2`, `ink-3`, `accent`,
`accent-ink`, `border`, `rule`, plus `headFont`, `bodyFont`, `googleFont` and
`headWeight`. `customCss` takes raw CSS for anything else.
