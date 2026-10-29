<div align="center">

# Workflow Name

One or two sentences: what it makes and how. Name the model.

![Model](https://img.shields.io/badge/model-MODEL-313131)
![Type](https://img.shields.io/badge/type-TYPE-0b8ce9)
![Output](https://img.shields.io/badge/output-OUTPUT-f0ff41)

</div>

| | |
| --- | --- |
| **What it makes** | The output, in plain words: length, resolution, aspect ratio, sound. |
| **How it works** | The main Nodes and how the inputs flow through them. |
| **Why it's worth a look** | The technique someone can reuse on their own project. |

## Contents

- [01 · Shared on](#01--shared-on)
- [02 · Files](#02--files)
- [03 · Run on Comfy Cloud](#03--run-on-comfy-cloud)
- [04 · Run on Comfy Desktop or a local ComfyUI](#04--run-on-comfy-desktop-or-a-local-comfyui)
- [05 · Inputs](#05--inputs)
- [06 · Make it your own](#06--make-it-your-own)
- [07 · Troubleshooting](#07--troubleshooting)

## 01 · Shared on

| Channel | Link |
| --- | --- |
| X | _Not yet shared._ |
| Discord | _Not yet shared._ |
| LinkedIn | _Not yet shared._ |
| Reddit | _Not yet shared._ |

## 02 · Files

| File | What it is |
| --- | --- |
| [SLUG_local.json](SLUG_local.json) | The Workflow for Comfy Desktop or a local ComfyUI. |
| [Open in Comfy Cloud](CLOUD_LINK) | The Workflow on Comfy Cloud. Requires a Comfy account. |
| [media/FILE](media/FILE) | A sample input. Say which input it fills. |

## 03 · Run on Comfy Cloud

| Step | What to do |
| --- | --- |
| Open | [Open in Comfy Cloud](CLOUD_LINK). Sign in first if the canvas opens empty. |
| Run | What to fill in, then press **Run**. |
| Cost | Credits per run, from the estimate on the Node. |

<!-- Keep this caution only when the Workflow has a Partner Node. -->
> [!CAUTION]
> Before you run, check the credit estimate above the Partner Node. It changes with the settings.

## 04 · Run on Comfy Desktop or a local ComfyUI

Say what differs from the Cloud version, if anything.

| Step | What to do |
| --- | --- |
| Requirements | Minimum ComfyUI or Comfy Desktop version, VRAM, and a Comfy account if there are Partner Nodes. |
| Custom Nodes | Each pack with a link, or "None". |
| Models | See the table below, or "None". |
| Copy the inputs | Copy the input files from `media/` into `ComfyUI/input`. The screenshots are not needed. |
| Load | Drag `SLUG_local.json` onto the canvas. |
| Run | Press **Run**. Say where the output saves. |

| Model file | Folder | Size | Download |
| --- | --- | --- | --- |
| `model.safetensors` | `ComfyUI/models/diffusion_models` | 0 GB | [link](URL) |

<!-- Keep this note only when the Workflow has a Partner Node. -->
> [!NOTE]
> MODEL is a Partner Node. It runs on the provider's servers, so you don't need a GPU. When ComfyUI runs on your machine, the Node still sends the job to the provider through Comfy and spends Comfy Credits.

## 05 · Inputs

| Input | File or value | What it controls |
| --- | --- | --- |
| | | |

<img src="media/screenshot-inputs.png" alt="Describe what the screenshot shows" width="720">

*Caption: what to look at in the screenshot.*

| Setting | Value |
| --- | --- |
| | |

## 06 · Make it your own

| Change | How |
| --- | --- |
| | |

## 07 · Troubleshooting

| Problem | Try this |
| --- | --- |
| A `Load Image` or `Load Video` Node shows a missing file | The file is not in `ComfyUI/input`, or its name changed. The names must match exactly. |
| Red Nodes after loading | A Custom Node is missing. Open **Manager > Install Missing Custom Nodes**, then restart ComfyUI. |
