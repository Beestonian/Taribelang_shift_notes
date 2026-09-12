# Taribelang shift notes — branching scenario

The opening scenario for the shift-notes learning module. Built with
[Switchback](https://switchback.dev); delivered as a single page and embedded
in Articulate Rise 360 via an iframe.

## Files

| File | What it is |
|---|---|
| `index.html` | The player. Uploaded once. Don't edit by hand. |
| `scenario.json` | The scenario. **This is the only file you normally change.** |

`index.html` fetches `scenario.json` from alongside itself at load, with a
timestamp query so no cache can stale it. If that fetch fails — opened from
disk, or served without the JSON — it falls back to a copy baked into the page,
so the file still works offline.

## Editing

**Small text changes:** edit `scenario.json` here on GitHub and commit. Pages
redeploys in about a minute and the Rise embed picks it up on next load.

**Structural changes:** open the live URL with `?edit` on the end. That opens
the Switchback authoring canvas loaded with the live scenario. When you're
done: Export → *Copy JSON only* → paste over `scenario.json` and commit.

If a banner says *"Restored the draft saved in this browser"*, click
**Discard and reload published** first — otherwise you're editing a stale local
draft rather than what's live.

## The lock

`scenario.json` contains `"locked": true`. That hides the **Build** button from
learners in the embedded player. `?edit` still works for authors. Keep the flag
when pasting new JSON over the file, or the button comes back for everyone.

## Embedding in Rise

Rise → Embed block:

```html
<iframe src="https://beestonian.github.io/Taribelang_shift_notes/" width="100%" height="760" style="border:0"></iframe>
```
