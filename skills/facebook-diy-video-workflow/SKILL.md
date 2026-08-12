---
name: facebook-diy-video-workflow
description: Create Facebook short-video materials for North American mature audiences with the author's field-tested prompts. Use when the user asks for a Facebook spoken sales script, DIY reference-video recreation, post-script multi-scene product images, or first-person factory unboxing images. Route any workflow that mentions unboxing to the unboxing branch; otherwise generate multi-scene product displays after the spoken script. Treat all bundled prompt files as immutable source text.
---

# Facebook DIY Video Workflow

Use the author's original prompts without rewriting them.

## Preserve Prompt Integrity

- Do not edit, rewrite, optimize, translate, condense, extend, or merge any bundled prompt.
- Read the selected reference file completely before using it.
- Keep the stored prompt text unchanged. Supply product details and attachments as separate user inputs.
- Do not fill an unfinished field or infer a missing production step unless the user explicitly provides that information.
- Pass new constraints alongside the original prompt instead of modifying the prompt file.

## Select a Prompt

- For a Facebook mature-audience spoken sales script or the user's "GPT full workflow," read and use [references/gpt-full-workflow.md](references/gpt-full-workflow.md) verbatim.
- For DIY reference-video analysis, production-step extraction, and a 15-second AI-video recreation script, read and use [references/video-breakdown-recreation-prompt.md](references/video-breakdown-recreation-prompt.md) verbatim.
- After generating a spoken script, use [references/multi-scene-product-display-prompt.md](references/multi-scene-product-display-prompt.md) verbatim by default.
- If the input, script, or requested workflow mentions unboxing or opening the package, skip the default multi-scene branch and use [references/factory-old-man-unboxing-prompt.md](references/factory-old-man-unboxing-prompt.md) verbatim.
- If the user explicitly requests both workflows, run them separately in the requested order. Do not combine their source text into a third prompt.

## Route Post-Script Images

Apply this routing after the spoken script is complete:

1. Scan the user's request and generated workflow for unboxing, opening the box, opening the package, or equivalent intent in any language.
2. If unboxing is present, require image 1 as the product and size source plus images 2, 3, and 4 as box-action references. Then run the original unboxing prompt. Produce three independent 9:16 images and a separate grid overview as requested by that prompt.
3. Otherwise require both the product image and a size-comparison image. Then run the original multi-scene prompt. Produce three separate 9:16 image files, never a grid, collage, split screen, or combined image.
4. If a required image is missing, pause this image branch and ask only for the missing image. Do not infer product dimensions.
5. If the image tool can generate only one image per call, continue until the branch's required independent images are complete.

The unboxing branch overrides the multi-scene prohibition on grids only for its separate grid deliverable. Never replace its three independent images with the grid.

## Run the Workflow

1. Identify which prompt matches the request and apply the post-script image route when a spoken script is generated.
2. Confirm the required product image and reference video are available when the selected prompt depends on them.
3. Submit the original prompt together with the user's attachments and separately supplied facts.
4. Follow the output format required by the selected prompt exactly.
5. Preserve product truth: describe a DIY kit as a DIY kit, not as a finished handmade product.

## Repository Boundaries

Keep archives, product images, reference videos, generated media, and temporary files outside this Skill. Users provide them at runtime.
