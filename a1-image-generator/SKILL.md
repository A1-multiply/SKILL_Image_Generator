---
name: a1-image-generator
description: Generate multiple AI images from a user concept, text, or reference. Use when the user wants several image variations, concept-matched images, prompts for image generation, thumbnails, illustrations, or visual sets, and the workflow must first ask whether references exist, request any uploaded text or images, ask the desired direction, and ask the total number of images before generating.
---

# A1 Image Generator

## Goal

Collect only the minimum needed information, then generate a batch of images that match the user's concept.

## Always Ask In This Order

1. Ask whether the user has any reference material.
2. If yes, ask them to upload or paste the text/image.
3. After reviewing what they shared, ask how they want the images to be made.
4. Ask how many images to generate in total.

If something is still missing, ask only for that missing piece.

## Approval Rule

If a yes/no approval is ever needed, ask it once only.
Do not repeat the same approval question unless the user changes the request.

## Workflow

1. If no reference is provided, ask for one compact reference question first.
2. If text or images are provided, summarize the concept briefly before doing anything else.
3. Ask the output direction after the summary, such as realistic, editorial, product, thumbnail, ad, sticker, anime, or close-match to the reference.
4. Ask for the total image count.
5. Generate exactly that many images unless the platform requires batching.

## Output Storage

- Always use a local `image/` folder in the current skill or repo root as the standard output folder.
- Create `image/` if it does not exist.
- Save every generated image into `image/` using a stable name per run.
- Keep the same relative `image/` path in every environment so the workflow behaves the same after download or git clone.
- If a tool returns files somewhere else, copy them into `image/` and keep the original unless the user asks otherwise.

## Token Discipline

- Keep each question short.
- Do not explain the whole workflow unless the user asks.
- Do not write long prompt theory.
- Reuse one shared style anchor for the whole batch.
- Vary only the parts needed to match the user's request.

## Image Guidance

- Preserve the subject, mood, palette, composition, and style cues from the reference when relevant.
- Make outputs consistent when the user wants a matched set.
- Make outputs diverse when the user wants options.
- Ask for aspect ratio or text-in-image only if it matters to the result.

