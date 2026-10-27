---
name: add-shared-workflow
description: Add and document a ComfyUI workflow shared on X, Discord, LinkedIn or Reddit to the Comfy-Org/workflows repo, using the shared/_template layout and README style.
---

# Add a shared workflow

Utilize when a user hands over a ComfyUI workflow (a zip, a JSON file, or a folder) that was or will be shared on social channels, and wants it added to the official workflows repo.

Repo: `Comfy-Org/workflows`. Template: `shared/_template/README.md`. Reference entry: `shared/haunted-subway/`. Read both before writing.

## Inputs to collect

Ask only for what is missing:

- The workflow file or zip, with its input media.
- The slug. Default: the workflow name, lowercase, hyphens, no spaces (`haunted-subway`).
- The Comfy Cloud link, if there is one.
- Post links per channel (X, Discord, LinkedIn, Reddit). Missing ones stay `_Not yet shared._`.
- A screenshots folder, often `~/Desktop/workflow-screenshots/<name>`. Request folder access if it is not connected.

X and t.co links can't be fetched. Don't try workarounds; ask the user for the post text if you need it.

## Layout

```text
shared/<slug>/
  README.md
  <slug>_local.json     Desktop or local ComfyUI version
  <slug>_cloud.json     only if the user provides one
  media/                inputs the workflow loads, plus screenshot-*.png for the README
```

Only create files that exist. Never rename a folder after a post links to it. Leave `cloud/` and `tutorial_workflows/` alone; they are legacy and other posts link to them.

## Steps

1. Unzip into a scratch folder, never into the repo. Drop `__MACOSX/` and `.DS_Store`.
2. Inspect the workflow JSON. This script lists every node, its pack and version, model files, and the files the Load nodes expect:

```python
import json, sys
d = json.load(open(sys.argv[1]))
nodes = d.get("nodes", []) + [n for s in d.get("definitions", {}).get("subgraphs", []) for n in s.get("nodes", [])]
for n in nodes:
    p = n.get("properties") or {}
    wv = n.get("widgets_values")
    short = [v[:80] if isinstance(v, str) else v for v in wv] if isinstance(wv, list) else wv
    print(n["id"], n["type"], n.get("title", ""), p.get("cnr_id", ""), p.get("ver", ""), short)
    for m in p.get("models", []) or []:
        print("   MODEL", m)
print("frontend", (d.get("extra") or {}).get("frontendVersion"))
```

   From the output, note:
   - Custom node packs: any `cnr_id` other than `comfy-core`. List each with a link.
   - Model files: from `properties.models` and loader widgets. Record folder, size and download URL.
   - Partner nodes (API nodes such as ByteDance, Kling, Veo, Gemini, OpenAI): these spend credits even on a local install. Keep the template's caution and note.
   - Load nodes and the exact filenames they expect.
   - Key settings (model, resolution, ratio, duration, audio, seed mode) and the prompt.
3. Rename media to lowercase hyphenated names (`Subway 1.png` -> `subway-1.png`). Update each Load node's `widgets_values[0]` and title in the JSON to match, then save it as `<slug>_local.json`. Tell Joshua you renamed them.
4. Copy screenshots into `media/` as `screenshot-<what>.png` with `cp -n`. Read each image before writing its alt text and caption. If a screenshot shows old filenames, say so in the caption.
5. Copy `shared/_template/README.md` to `shared/<slug>/README.md` and fill every section. Replace `SLUG`, `CLOUD_LINK`, `MODEL` and the badge placeholders. Delete the HTML comments and any partner-node caution or note that does not apply. Add sections when the workflow earns them; Haunted Subway adds "The prompt".
6. Add a row to the table in the root `README.md` under "02 · Workflows", newest first: name linked to the folder, what it makes, Cloud link, local JSON link, channels.

## Checks before handing back

- No API keys, tokens, `/Users/` or `C:\\` paths in the JSON: `grep -n "api_key\|/Users/\|C:\\\\" <file>`.
- Each media file under 10 MB. Larger media goes in a release; ask the user.
- Every relative link in the README points at a file that exists.
- Prose follows the docs style: no em dashes, short sentences, present tense, "use" not "utilize". `grep -n "—" README.md` returns nothing.
- Don't state credit costs, VRAM or model sizes you have not seen. Read the estimate from a screenshot or leave a TODO.
- `git status` shows only the new folder and the root README.

## Finish

Don't commit, push or open a PR without the user's go-ahead. Report what you added, what you renamed, and what is still a placeholder (Cloud JSON, missing channel links, unresolved short links).
