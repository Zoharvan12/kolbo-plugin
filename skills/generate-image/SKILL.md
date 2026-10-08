---
name: generate-image
description: Generate or edit images with Kolbo.AI. Use when the user asks to create, generate, render, edit, restyle or upscale an image, illustration, poster, product shot, character, scene or visual concept — and when they want a character, product or brand look to stay consistent across images.
---

# Generate images with Kolbo

First load the bundled `kolbo` skill and its matching model/workflow reference. Its routing, live catalog and approval rules take precedence over these quick-start notes. For a micro-drama series, follow the Micro-Drama Studio route in that skill.

Use the `generate_image` MCP tool. Deliver the actual image — never just describe what you would make.

## Before you generate

- Call `list_models` when the user names a look, a budget, or a capability you are unsure of. Model strengths differ; do not guess an identifier.
- Everything in Kolbo lives in a **project**. If the user names one, call `list_projects` once, then pass that same `project_id` on every later call in the conversation. There is no server-side memory of it.
- Generation spends credits. For anything large or repeated, say what it will cost and get agreement first. `check_credits` reports the balance.

## Visual DNA — consistent characters, products and brands

A Visual DNA keeps the same face, product or brand look across images.

**Passing `visual_dna_ids` is not enough.** Every DNA in play must ALSO be tagged inside the prompt text by name:

```
@Kobi stands on a rooftop at dusk, city lights behind him
```

Resolve names with `list_visual_dnas` first. Moodboards work the same way with `#Name` (`list_moodboards`).

A bare name with no `@` sends the model nothing — the image comes back with the wrong face.

## Writing the prompt

- Describe the subject, setting, lighting, lens and mood in plain sentences. Concrete beats ornate.
- State the aspect ratio the user asked for rather than assuming square.
- For an edit, attach the source image as a reference and describe the change imperatively ("replace the background with…"), not as a fresh scene description.

## After it returns

Report the model used and the credits spent. Do not paste raw URLs as the whole reply — the client renders results itself.
