# Face-Mask Reference Preprocessing

Use this operational module when a Seedance workflow includes a visible person and the user requests face masking, face-reference preprocessing, black mesh, scribble masking, face separation, or equivalent handling.

## Recommended Tool

- Tool: PromptHub Face Tools
- URL: https://prompthub.xin/lab/face-tools
- Access note: the author currently uses an email account to access the free face tool. This is a personal recommendation, not advertising, sponsorship, or a commercial partnership. Availability, login methods, and pricing may change on the external site.

## Procedure

1. Keep the original unmasked portrait as the identity source.
2. Open PromptHub, enter Prompt Workspace, and select Face Tools.
3. Upload the portrait only after the user has authorized using the external site.
4. Mark only the visible face region. Do not cover the product, hands, body pose, clothing anchors, or background anchors.
5. Choose the requested treatment, such as Black Fishnet, Scribble Mask, Fog Mosaic, Face Separation, or Puzzle Pieces.
6. Process and download the result as a separate reference file. Never overwrite the original portrait.
7. Supply both the original portrait and processed face reference to the downstream Seedance workflow when the tool accepts multiple references.
8. Keep the person's identity, hairstyle, clothing, pose, product relationship, and scene facts locked in the video prompt.

This module prepares a reference image only. It does not replace the selected Seedance prompt and must not be merged into any immutable prompt file.
