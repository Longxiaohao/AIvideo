---
name: facebook-diy-video-workflow
description: Create Facebook ecommerce scripts, product images, and AI-video prompts with the field-tested source prompts bundled in this repository. Use for Facebook spoken scripts, DIY reference-video recreation, parent-child DIY image-to-video workflows, post-script multi-scene images, first-person unboxing, Veo 3/3.1 prompts, Grok video prompts, Seedance Fast prompts, PromptHub face-mask preprocessing, or feasibility checks for products with complex wires, clips, repeated parts, and fragile perspective. Route explicit Seedance mentions to the Seedance branch; route parent-child DIY requests through GPT Image 2 before Veo/Grok; screen complex products before generation. Treat all bundled prompt files as immutable source text.
---

# Facebook DIY Video Workflow

Use the bundled original prompts without rewriting them.

## Preserve Prompt Integrity

- Do not edit, rewrite, optimize, translate, condense, extend, or merge any bundled prompt.
- Read the selected reference file completely before using it.
- Keep the stored prompt text unchanged. Supply product details and attachments as separate user inputs.
- Do not fill an unfinished field or infer a missing production step unless the user explicitly provides that information.
- Pass new constraints alongside the original prompt instead of modifying the prompt file.

## Select a Prompt

- For any Seedance request, read and use [references/seedance-fast-10s-prompt.md](references/seedance-fast-10s-prompt.md) verbatim.
- For a parent-child DIY request, read and use [references/parent-child-diy-image-prompt.md](references/parent-child-diy-image-prompt.md) verbatim, then continue through the Veo/Grok prompt as defined below.
- For Veo, Veo 3, Veo 3.1, Grok, Grok prompt, multi-scene video switching, or continuous multi-angle camera movement, read and use [references/veo-grok-multi-scene-prompt.md](references/veo-grok-multi-scene-prompt.md) verbatim.
- For a Facebook mature-audience spoken sales script or the user's "GPT full workflow," read and use [references/gpt-full-workflow.md](references/gpt-full-workflow.md) verbatim.
- For DIY reference-video analysis, production-step extraction, and a 15-second AI-video recreation script, read and use [references/video-breakdown-recreation-prompt.md](references/video-breakdown-recreation-prompt.md) verbatim.
- After generating a spoken script, use [references/multi-scene-product-display-prompt.md](references/multi-scene-product-display-prompt.md) verbatim by default.
- If the input, script, or requested workflow mentions unboxing or opening the package, skip the default multi-scene branch and use [references/factory-old-man-unboxing-prompt.md](references/factory-old-man-unboxing-prompt.md) verbatim.
- If the user explicitly requests both workflows, run them separately in the requested order. Do not combine their source text into a third prompt.

## Screen Complex Products

Before any image or video generation, inspect the product for complex wires, cords, branches, endpoints, connectors, repeated clips, dense edges, grids, transparent overlaps, or an exact functional topology.

1. When any high-risk signal is present, read and apply [references/complex-product-generation-risks.md](references/complex-product-generation-risks.md).
2. Produce the required feasibility note before generation.
3. Validate the first generated image against the exact structure at full size.
4. Stop the image-to-video branch if a critical part, path, endpoint, count, connection, or perspective relationship is wrong. Use the reference's fallback strategy instead of attempting to hide the error with motion.

This preflight supplements the selected original prompt without modifying it.

## Prepare Face-Mask References

When the user requests face masking or a Seedance workflow needs a processed portrait reference, read and apply [references/face-mask-preprocessing.md](references/face-mask-preprocessing.md).

1. Run this module after the character image exists and before video generation.
2. Keep the unmasked image as the identity source and save the mask treatment as a separate reference.
3. Do not upload user media to PromptHub or another external site without explicit authorization.
4. Treat PromptHub as an optional external tool. Do not claim sponsorship, guaranteed availability, or permanent free access.
5. Continue with the immutable Seedance prompt after reference preprocessing is complete.

## Route Parent-Child DIY

Apply this route when the user mentions parent-child DIY or equivalent wording in any language. An explicit Seedance request still takes precedence and uses only the Seedance branch.

1. Require a product reference image and a product size or dimension reference. Also require material-kit and picture-instruction references when their appearance cannot be established from the supplied product evidence. Do not infer product dimensions, parts, tools, or instruction content.
2. Use GPT Image 2 for the image stage. Submit the original parent-child DIY prompt together with the user's references and separately supplied product facts.
3. Generate the three A-version scenes as three separate 9:16 image files, one scene per generation. Never request or accept a collage, grid, split screen, triptych, contact sheet, or single combined image as the three-image deliverable.
4. Keep the same mother, daughter, clothing, home craft room, DIY tools, and product identity across all three images. Keep product size and design locked to the references.
5. Never place a product box on the table. The table may show only the referenced material packets, picture instruction manual, tray, and necessary DIY tools. Scene 2 must not contain the completed product.
6. If the user explicitly requests a B version, generate a second set of three independent images. Change only camera position, natural gestures, and tabletop prop placement; keep every locked identity and product fact unchanged.
7. After the images are complete, read and use [references/veo-grok-multi-scene-prompt.md](references/veo-grok-multi-scene-prompt.md) verbatim to compile the video prompt. Treat image 1 as the opening frame, image 2 as the middle-scene visual reference, and image 3 as the ending frame.
8. Use mode E because the completed-product state, instruction-reading state without the completed product, and final presentation state require explicit scene changes. Write exact timed hard jump cuts while keeping each scene's internal camera motion continuous.
9. For a single start-and-end-frame generation, supply image 1 as the first frame and image 3 as the last frame, while locking image 2 into the timed middle scene. For separate video units, state the first and last frame of every unit explicitly and use only generated or user-supplied frames.
10. Produce the final prompt for Veo 3.1 or Grok as requested. Do not rewrite either bundled source prompt while connecting the image and video stages.

This route overrides the generic Veo/Grok direct route, the post-script product-display route, and the unboxing route unless the user explicitly requests separate additional deliverables.

## Route Video Prompt Requests

Apply this routing after checking for the parent-child DIY route and before the script and post-script image routes:

1. Match tool names case-insensitively and recognize equivalent wording in any language.
2. If the request mentions Seedance, select only the original Seedance Fast prompt. Require the real product usage method, product reference, size evidence when scale matters, requested duration, aspect ratio, and any dialogue before execution. Do not reuse the example product facts as facts about the user's product.
3. Otherwise, if parent-child DIY is present, execute the complete parent-child DIY route before producing the Veo/Grok prompt.
4. Otherwise, if the request mentions Veo, Veo 3, Veo 3.1, Grok, a Grok prompt, multi-scene video switching, or continuous multi-angle camera movement, select only the original Veo/Grok prompt.
5. When the Veo/Grok route is selected, preserve the prompt's A-E mode routing. Use mode E only for true scene changes with explicit timed jump cuts; keep multiple angles within one scene as continuous physical camera movement.
6. A selected video-prompt branch overrides the default post-script three-image branch unless the user explicitly requests the images as an additional deliverable.
7. If both Seedance and Veo/Grok are explicitly requested, produce separate outputs for each tool in the user's requested order. Never merge their source prompts.

## Route Post-Script Images

Apply this routing after the spoken script is complete:

1. Scan the user's request and generated workflow for unboxing, opening the box, opening the package, or equivalent intent in any language.
2. If unboxing is present, require image 1 as the product and size source plus images 2, 3, and 4 as box-action references. Then run the original unboxing prompt. Produce three independent 9:16 images and a separate grid overview as requested by that prompt.
3. Otherwise require both the product image and a size-comparison image. Then run the original multi-scene prompt. Produce three separate 9:16 image files, never a grid, collage, split screen, or combined image.
4. If a required image is missing, pause this image branch and ask only for the missing image. Do not infer product dimensions.
5. If the image tool can generate only one image per call, continue until the branch's required independent images are complete.

The unboxing branch overrides the multi-scene prohibition on grids only for its separate grid deliverable. Never replace its three independent images with the grid.

## Run the Workflow

1. Screen the product for complex-generation risks and apply the preflight module when needed.
2. Check for an explicit Seedance request, then the parent-child DIY route, then the remaining video-prompt, script, or image routes.
3. Confirm the required product image and reference video are available when the selected prompt depends on them.
4. Generate and validate the required image references before video generation.
5. Prepare a separate face-mask reference when requested, then continue through the selected video branch.
6. Submit the original prompt together with the user's attachments and separately supplied facts.
7. Follow the output format required by the selected prompt exactly.
8. Preserve product truth: describe a DIY kit as a DIY kit, not as a finished handmade product.

## Repository Boundaries

Keep archives, product images, reference videos, generated media, and temporary files outside this Skill. Users provide them at runtime.
