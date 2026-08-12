<div align="center">

# Cross-Border E-commerce AI Video Production

**Codex Skills and field-tested prompt SOPs for producing complex AI commerce videos at lower cost.**

Write the script and voiceover first, generate images, turn images into video, process face masks, build a high-retention grid opening, and use Codex or Claude to break down reference videos.

[![GitHub stars](https://img.shields.io/github/stars/Longxiaohao/AIvideo?style=flat-square)](https://github.com/Longxiaohao/AIvideo/stargazers)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](./LICENSE)
[![Codex Skills](https://img.shields.io/badge/Codex-Skills-black.svg?style=flat-square)](./skills)
[![Video Tools](https://img.shields.io/badge/video-Veo%20%7C%20Grok%20%7C%20Seedance-orange.svg?style=flat-square)](#automatic-routing)

[中文](./README.md) | **English**

</div>

---

## Why This Project Exists

The practical challenge in cross-border e-commerce video production is no longer access to AI models. It is finding a reliable way to achieve useful results at a lower cost. Paid tools are not always required: the free Doubao Seedance Fast workflow, together with tools such as Grok and Veo, already covers a large part of script, image, and video generation.

These Skills organize mature prompts and routing rules from hands-on production into a reusable SOP. They are designed for creators who need a low-cost pipeline for commerce videos and for job seekers who want practical AI-video production experience and portfolio work.

Once the source materials are ready, the SOP makes it possible to combine tools flexibly and target a relatively complex AI commerce video within one hour. The one-hour figure is a workflow target, not a fixed guarantee for every product, network condition, or generation queue.

This repository preserves the author's prompts as they are used in practice. The Skills only identify tasks, validate inputs, and route branches. They do not rewrite, condense, or creatively alter the source prompts.

## Core Workflow

```mermaid
flowchart LR
    A["Codex / Claude<br/>Break down winning videos"] --> B["Script and voiceover"]
    B --> C["Product and scene images"]
    C --> D["Veo / Grok / Seedance<br/>Image-to-video"]
    D --> E["Doubao face masking"]
    E --> F["Grid-style viral opening"]
    F --> G["Editing and final video"]
```

1. Use Codex or Claude to break down a successful reference video and extract its opening structure, shots, production actions, and pacing.
2. Write the script and voiceover from verified product facts, locking the audience, dialogue, scenes, and target duration.
3. Generate product displays, parent-child DIY scenes, unboxing images, or first and last frames from the product image, dimensions, and script.
4. Select Veo 3.1, Grok, or the free Doubao Seedance Fast according to budget and task complexity.
5. Use Doubao face masking to address character consistency or local visual issues.
6. Build a high-retention opening from grid assets, then complete standard editing, sound, and delivery.

## Tool Fallback Strategy

The same script and assets can move between tools according to budget, queue time, and generation quality without rebuilding the entire workflow.

| Task | Preferred tool | Lower-cost or fallback path | What the Skill handles |
| --- | --- | --- | --- |
| Winning-video breakdown | Codex / Claude | Any Agent that can inspect video and images | Extracts shots, actions, pacing, and reusable structure |
| Complex multi-scene video | Veo 3.1 | Grok | Defines jump-cut timing, multi-angle camera paths, and continuity locks |
| Fast image-to-video | Grok / Veo | Doubao Seedance Fast | Compresses the plan into a physically executable short-video unit |
| Human-shot correction | Doubao face masking | Regenerate from the first frame or character reference | Preserves character, product, and dialogue anchors |
| High-retention opening | Independent grid assets | Reorder existing shots | Breaks down the opening structure and organizes shot order |

Fallback changes the execution tool only. It must not alter verified product facts, exact dialogue, scale, assembly steps, or any original prompt.

## Capabilities

- **Facebook mature-audience voiceovers**: generate natural spoken scripts for North American audiences aged 35–45 from product references.
- **DIY reference-video recreation**: analyze real production steps and generate a 15-second Facebook AI-video script.
- **Parent-child DIY image-to-video**: generate three independent 9:16 American family DIY images with GPT Image 2, then compile a Veo 3.1 or Grok first-and-last-frame video prompt.
- **Multi-scene product display**: after the voiceover, generate three independent 9:16 product images in distinct scenes by default.
- **First-person unboxing**: route unboxing intent to the factory-old-man first-person branch.
- **Veo / Grok video prompts**: handle talking people, product demonstrations, product-only scenes, continuous takes, and explicit multi-scene jump cuts.
- **Seedance Fast prompts**: generate compact, continuous, physically executable video units from the product's real usage method.
- **Cinematic giant visuals**: create image or video prompts for Chinese dragons, deities, giants, mysterious beings, and disaster-scale scenes.

## Who It Is For

- Individuals and teams producing TikTok, Facebook, or other cross-border e-commerce videos.
- Creators building a stable AI-video pipeline with free or lower-cost tools.
- Job seekers targeting AI video, AIGC content, or cross-border e-commerce creative roles.
- Anyone who needs to assemble a portfolio piece, test video, or complex sample quickly.

## Automatic Routing

`facebook-diy-video-workflow` selects a branch from natural-language intent:

| User mentions | Automatic action |
| --- | --- |
| `Seedance` | Prioritize the Seedance Fast branch |
| Parent-child DIY, mother-daughter DIY, family crafting | Generate three independent GPT Image 2 images, then enter the Veo/Grok first-and-last-frame branch |
| `Veo`, `Veo 3/3.1`, or `Grok` | Enter the Veo/Grok multi-scene and continuous multi-angle camera branch |
| Unboxing, opening the box, or opening the package | Enter the factory-old-man first-person unboxing branch |
| Facebook voiceover, mature-audience voiceover, or GPT full workflow | Enter the Facebook spoken-script branch |
| DIY, reference-video breakdown, or production-step recreation | Enter the DIY reference-video recreation branch |
| Voiceover complete with no unboxing or video-tool trigger | Generate three independent multi-scene product images by default |

An explicit Seedance request takes priority. Parent-child DIY overrides the generic product-image, unboxing, and direct Veo/Grok branches unless the user explicitly requests them as separate deliverables. When both Seedance and Veo/Grok are requested, the Skill produces separate outputs in the requested order and never merges their source prompts.

## Installation

### Ask an AI Assistant to Install It (Recommended)

Send this to Codex:

> Install the AIvideo Skills from GitHub:
>
> https://github.com/Longxiaohao/AIvideo
>
> Install `facebook-diy-video-workflow` and `cinematic-giant-visual-prompts`, validate both Skills, and tell me whether I need to refresh the session.

### Manual Installation

Clone the repository:

```bash
git clone https://github.com/Longxiaohao/AIvideo.git
cd AIvideo
```

Windows PowerShell:

```powershell
Copy-Item -Recurse -Force .\skills\facebook-diy-video-workflow "$env:USERPROFILE\.codex\skills\facebook-diy-video-workflow"
Copy-Item -Recurse -Force .\skills\cinematic-giant-visual-prompts "$env:USERPROFILE\.codex\skills\cinematic-giant-visual-prompts"
```

macOS / Linux:

```bash
mkdir -p ~/.codex/skills
cp -R skills/facebook-diy-video-workflow ~/.codex/skills/
cp -R skills/cinematic-giant-visual-prompts ~/.codex/skills/
```

After installing or updating, refresh the current session so Codex can rediscover the Skills.

## Usage

Use natural language after installation. You do not need to select reference files manually.

| Example request | What the Skill does |
| --- | --- |
| "Write a Facebook mature-audience voiceover from this product image." | Runs the GPT full-workflow voiceover prompt |
| "Analyze this DIY reference video and recreate its production steps." | Runs the DIY reference-video recreation prompt |
| "Create parent-child DIY scenes, then make a Veo 3.1 video." | Generates three separate Image 2 frames and uses images 1 and 3 as the first and last frames |
| "Create three different product-display scenes after the voiceover." | Requires product and size references, then generates three independent 9:16 images |
| "Make a factory first-person unboxing for this product." | Requires product dimensions and action references, then enters the unboxing branch |
| "Turn this script into a Veo 3.1 multi-scene prompt." | Outputs mode selection, lock card, camera path, timeline, and final Veo prompt |
| "Write a Grok multi-angle product-video prompt." | Applies the Veo/Grok continuous multi-angle camera rules |
| "Write a 10-second Seedance prompt from the real usage method." | Prioritizes the Seedance Fast branch |
| "Create a video prompt for a Chinese dragon over a stormy city." | Uses the cinematic giant-visual Skill |

Explicit invocation is also supported:

```text
Use $facebook-diy-video-workflow to turn my product facts and reference images into a Veo 3.1 prompt.
```

```text
Use $cinematic-giant-visual-prompts to create a realistic Chinese dragon video prompt.
```

## Recommended Inputs

- Finished-product, front, side, and detail images.
- A dimensions image or a scale comparison with a hand, person, or common object.
- Correct usage, assembly order, contact points, and action results.
- A winning reference video, first frame, character master image, or packaging reference.
- Product, dimensions, material-kit, DIY-tool, and picture-instruction references for parent-child DIY.
- Dialogue, voiceover, and sound requirements that must remain verbatim.
- Target tool, duration, aspect ratio, scene count, and whether jump cuts are allowed.

If missing information would change product scale, production method, or a key action, the Skill asks for it instead of inventing it.

## Project Structure

```text
AIvideo/
├── README.md
├── README.en.md
├── LICENSE
└── skills/
    ├── facebook-diy-video-workflow/
    │   ├── SKILL.md
    │   ├── agents/
    │   │   └── openai.yaml
    │   └── references/
    │       ├── gpt-full-workflow.md
    │       ├── video-breakdown-recreation-prompt.md
    │       ├── multi-scene-product-display-prompt.md
    │       ├── factory-old-man-unboxing-prompt.md
    │       ├── parent-child-diy-image-prompt.md
    │       ├── veo-grok-multi-scene-prompt.md
    │       └── seedance-fast-10s-prompt.md
    └── cinematic-giant-visual-prompts/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        └── references/
            └── original-prompt.md
```

## Prompt Integrity

The reference prompts in this repository come from the author's real workflow:

- [`gpt-full-workflow.md`](./skills/facebook-diy-video-workflow/references/gpt-full-workflow.md): complete Facebook mature-audience voiceover workflow.
- [`video-breakdown-recreation-prompt.md`](./skills/facebook-diy-video-workflow/references/video-breakdown-recreation-prompt.md): DIY reference-video breakdown and recreation.
- [`multi-scene-product-display-prompt.md`](./skills/facebook-diy-video-workflow/references/multi-scene-product-display-prompt.md): three independent multi-scene product images.
- [`factory-old-man-unboxing-prompt.md`](./skills/facebook-diy-video-workflow/references/factory-old-man-unboxing-prompt.md): factory first-person unboxing.
- [`parent-child-diy-image-prompt.md`](./skills/facebook-diy-video-workflow/references/parent-child-diy-image-prompt.md): three independent parent-child DIY scene images.
- [`veo-grok-multi-scene-prompt.md`](./skills/facebook-diy-video-workflow/references/veo-grok-multi-scene-prompt.md): Veo/Grok continuous multi-angle camera work and multi-scene video.
- [`seedance-fast-10s-prompt.md`](./skills/facebook-diy-video-workflow/references/seedance-fast-10s-prompt.md): Seedance Fast video unit.
- [`original-prompt.md`](./skills/cinematic-giant-visual-prompts/references/original-prompt.md): cinematic giant image and video prompts.

The Skill wrapper may improve triggering and routing, but the reference prompts above remain immutable source text by default.

## Repository Boundaries

The repository contains only the instructions and prompts required by the Skills. Product images, reference videos, generated media, analysis caches, and archives stay outside GitHub and are supplied as runtime attachments.

## Contributing

[Issues](https://github.com/Longxiaohao/AIvideo/issues) are welcome for new tool routes, real failure cases, routing improvements, installation issues, and compatibility reports.

## License

MIT. See [LICENSE](./LICENSE).
