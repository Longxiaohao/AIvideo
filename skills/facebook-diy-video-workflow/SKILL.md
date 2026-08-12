---
name: facebook-diy-video-workflow
description: Create Facebook short-video materials for North American mature audiences with the author's field-tested prompts. Use when the user asks for a Facebook mature-audience spoken sales script from product images, or wants to analyze a reference DIY video and recreate its making steps as a 15-second 9:16 AI-video script. Treat the bundled prompt files as immutable source text.
---

# Facebook DIY Video Workflow

Use the author's original prompts without rewriting them.

## Preserve Prompt Integrity

- Do not edit, rewrite, optimize, translate, condense, extend, or merge either bundled prompt.
- Read the selected reference file completely before using it.
- Keep the stored prompt text unchanged. Supply product details and attachments as separate user inputs.
- Do not fill an unfinished field or infer a missing production step unless the user explicitly provides that information.
- Pass new constraints alongside the original prompt instead of modifying the prompt file.

## Select a Prompt

- For a Facebook mature-audience spoken sales script or the user's "GPT full workflow," read and use [references/gpt-full-workflow.md](references/gpt-full-workflow.md) verbatim.
- For DIY reference-video analysis, production-step extraction, and a 15-second AI-video recreation script, read and use [references/video-breakdown-recreation-prompt.md](references/video-breakdown-recreation-prompt.md) verbatim.
- If the user explicitly requests both workflows, run them separately in the requested order. Do not combine their source text into a third prompt.

## Run the Workflow

1. Identify which prompt matches the request.
2. Confirm the required product image and reference video are available when the selected prompt depends on them.
3. Submit the original prompt together with the user's attachments and separately supplied facts.
4. Follow the output format required by the selected prompt exactly.
5. Preserve product truth: describe a DIY kit as a DIY kit, not as a finished handmade product.

## Repository Boundaries

Keep archives, product images, reference videos, generated media, and temporary files outside this Skill. Users provide them at runtime.
