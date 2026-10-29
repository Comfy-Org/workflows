<div align="center">

# Comfy Workflows

The official home for ComfyUI Workflows that Comfy Org shares on X, Discord, LinkedIn and Reddit. Each post links here, and each Workflow comes in a version for Comfy Cloud and a version for Comfy Desktop or a local ComfyUI.

![Channels](https://img.shields.io/badge/shared%20on-X%20·%20Discord%20·%20LinkedIn%20·%20Reddit-313131)
![Runs on](https://img.shields.io/badge/runs%20on-Comfy%20Cloud%20·%20Desktop%20·%20Local-0b8ce9)
![License GPL-3.0](https://img.shields.io/badge/license-GPL--3.0-f0ff41)

</div>

| | |
| --- | --- |
| **What it is** | One folder per shared Workflow, with the Workflow files, a README that says what it makes and what it needs, and links back to every post that shared it. |
| **Who it's for** | Anyone who saw a Workflow in a post and wants to run it. Cloud users get a one-click link. Desktop and local users get a Workflow file with the models and Custom Nodes listed. |
| **How it's different** | A post on X can only hold a link. This repo holds the whole thing: both versions, the model list, the inputs and the media, in one place that every channel points to. |

## Contents

- [01 · Quick start](#01--quick-start)
- [02 · Workflows](#02--workflows)
- [03 · Cloud and local versions](#03--cloud-and-local-versions)
- [04 · Repo layout](#04--repo-layout)
- [05 · Add a Workflow](#05--add-a-workflow)
- [06 · Legacy Workflows](#06--legacy-workflows)
- [07 · Troubleshooting](#07--troubleshooting)
- [License](#license)

## 01 · Quick start

| Step | What to do |
| --- | --- |
| Find the Workflow | Open the post's link, or pick a Workflow from [02 · Workflows](#02--workflows). |
| On Comfy Cloud | Click the **Open in Comfy Cloud** link in the Workflow's README. Cloud has the models already. Runs spend Comfy Credits. |
| On Comfy Desktop or a local ComfyUI | Download `<slug>_local.json` and drag it onto the canvas. Install any missing Custom Nodes with **Manager > Install Missing Custom Nodes**. Download the models the README lists into the folders it names. |
| Run | Fill the inputs the README names and press **Run**. |

## 02 · Workflows

Workflows from posts live in [`shared/`](shared), one folder each. The table lists the most recent first.

| Workflow | Makes | Cloud | Local | Shared on |
| --- | --- | --- | --- | --- |
| [Car Transition](shared/car-transition) | A 10 s shot where a miniature Porsche on a train windowsill becomes a real car driving into a city at night, from two reference images (Seedance 2.5) | [Open](https://t.co/jAxGir8qij) | [JSON](shared/car-transition/car-transition_local.json) | [X](https://x.com/ComfyUI/status/2115451076799606868) |
| [Halloween SD](shared/halloween-sd) | An 18 s vertical anime Halloween short where one character changes costume on every beat, from a 3D blockout and seven reference images (Seedance 2.5) | [Open](https://t.co/2pO0ixzDbu) | [JSON](shared/halloween-sd/halloween-sd_local.json) | [X](https://x.com/ComfyUI/status/2113682376815779899) |
| [Haunted Subway](shared/haunted-subway) | A 21 s first-person horror short from a 3D blockout and four reference images (Seedance 2.5) | [Open](https://t.co/a2wZTjQGOJ) | [JSON](shared/haunted-subway/haunted-subway_local.json) | [X](https://x.com/ComfyUI/status/2115089830585704602) |

## 03 · Cloud and local versions

A Workflow often starts on Comfy Cloud, because Cloud has the models and a link is easy to share. The local version is the same idea, adjusted to run on your own GPU.

| | Cloud version | Local version |
| --- | --- | --- |
| File | `<slug>_cloud.json`, plus an **Open in Comfy Cloud** link | `<slug>_local.json` |
| Models | Already on Cloud | Listed in the README with a download link and the `ComfyUI/models` folder for each |
| Custom Nodes | Only the ones Cloud has | Listed in the README. Install them with ComfyUI Manager. |
| Partner Nodes | Billed in Comfy Credits | Need a Comfy account signed in to Comfy Desktop. Billed in Comfy Credits. |
| Cost | Comfy Credits per run | Free on your GPU, except Partner Nodes |

The two versions can differ. The local version may swap a model for a smaller one, or a Cloud-only Node for a Custom Node. The Workflow's README says what changed.

## 04 · Repo layout

```text
shared/
  <slug>/
    README.md            what it makes, links, models, inputs, notes
    <slug>_cloud.json    the version shared as a Comfy Cloud link
    <slug>_local.json    the version for Comfy Desktop or a local ComfyUI
    media/               preview image or video, and sample inputs when needed
  _template/             copy this to start a new workflow
cloud/                   legacy Cloud Workflows (see 06)
tutorial_workflows/      legacy tutorial Workflows (see 06)
```

| Rule | Why |
| --- | --- |
| The slug is lowercase with hyphens, such as `wan22-looped-restyler`. | Links stay readable and stable. |
| A folder holds only the versions that exist. A Cloud-only Workflow has no `_local.json`. | No empty files. |
| Workflow files are the UI format from **Workflow > Export**, not **Export (API)**. | People open them on the canvas. |
| Media stays small: a preview under 10 MB, and sample inputs only when the Workflow needs a specific one. | The repo stays quick to clone. Large media goes in a release. |
| Folder names never change after a post links to them. | A renamed folder breaks every post that linked it. |

## 05 · Add a Workflow

1. Copy `shared/_template` to `shared/<slug>`.
2. Add `<slug>_cloud.json`, `<slug>_local.json`, or both. Export each from the canvas with **Workflow > Export**.
3. Fill in the README: what it makes, the post links, the Cloud link, models, Custom Nodes and inputs.
4. Add a preview to `media/`.
5. Add a row to the table in [02 · Workflows](#02--workflows), newest first.
6. Run the local version on a fresh Comfy Desktop install before you post the link, so the model list is complete.

Before you post, check that the Workflow has no API keys, local file paths or private images in it.

## 06 · Legacy Workflows

These were added before the `shared/` layout. They stay where they are so existing links keep working.

**[`cloud/`](cloud)**, built for Comfy Cloud:

| File | What it is |
| --- | --- |
| [animatediff-weighted_ipadapters.json](cloud/animatediff-weighted_ipadapters.json) | AnimateDiff with weighted IPAdapters |
| [flux-image_upscaler.json](cloud/flux-image_upscaler.json) | Flux image upscaler |
| [multistyle-magazine-cover-nanobananapro.json](cloud/multistyle-magazine-cover-nanobananapro.json) | Multi-style magazine covers with Nano Banana Pro |
| [qwen_image_edit_2509.json](cloud/qwen_image_edit_2509.json) | Qwen Image Edit 2509 |
| [wan21-ati_trajectory.json](cloud/wan21-ati_trajectory.json) | Wan 2.1 ATI trajectory control |
| [wan21-wanmove_fl_path_animator.json](cloud/wan21-wanmove_fl_path_animator.json) | Wan 2.1 WanMove first and last frame path animator |
| [Wan22-6-key-frames.json](cloud/Wan22-6-key-frames.json) | Wan 2.2 with six key frames |
| [wan22-animate-auto-character_replace.json](cloud/wan22-animate-auto-character_replace.json) | Wan 2.2 Animate, automatic character replace |
| [wan22-animate-auto-full_scene.json](cloud/wan22-animate-auto-full_scene.json) | Wan 2.2 Animate, automatic full scene |
| [wan22-looped_restyler.json](cloud/wan22-looped_restyler.json) | Wan 2.2 looped restyler |

**[`tutorial_workflows/`](tutorial_workflows)**, from the Get Comfy With Comfy tutorials. Most need Custom Nodes and local models:

| File | What it is |
| --- | --- |
| [automated_music_video_generator-wan_22_animate-visualfrisson.json](tutorial_workflows/automated_music_video_generator-wan_22_animate-visualfrisson.json) | Automated music video generator with Wan 2.2 Animate, by VisualFrisson |
| [get_comfy_with_comfy-consistent_character_dataset_generator.json](tutorial_workflows/get_comfy_with_comfy-consistent_character_dataset_generator.json) | Consistent character dataset generator |
| [get_comfy_with_comfy-ovi-video_and_audio.json](tutorial_workflows/get_comfy_with_comfy-ovi-video_and_audio.json) | Ovi video and audio |
| [get_comfy_with_comfy-wan_22_animate.json](tutorial_workflows/get_comfy_with_comfy-wan_22_animate.json) | Wan 2.2 Animate |
| [Get_Comfy_With_Comfy_Wan_Alpha.json](tutorial_workflows/Get_Comfy_With_Comfy_Wan_Alpha.json) | Wan Alpha |

## 07 · Troubleshooting

| Problem | Try this |
| --- | --- |
| Red Nodes after loading | A Custom Node is missing. Open **Manager > Install Missing Custom Nodes**, install, and restart ComfyUI. The Workflow's README lists every pack. |
| "Value not in list" on a model loader | The model file is missing or in another folder. Check the README's model table for the file name and folder, then press `R` to refresh the Node. |
| A Partner Node asks you to sign in | Partner Nodes run a hosted model. Sign in to your Comfy account in Comfy Desktop. Each run spends Comfy Credits. |
| Out of memory on a local GPU | Lower the resolution or frame count, or use the smaller model the README suggests. The Cloud version runs on larger GPUs. |
| The Cloud link opens an empty canvas | Sign in to Comfy Cloud first, then open the link again. |

Something else wrong? Open an issue with the Workflow's slug, where you ran it, and the error text.

## License

GPL-3.0. See [LICENSE](LICENSE). Models and Custom Nodes keep their own licenses; each Workflow's README links them.
