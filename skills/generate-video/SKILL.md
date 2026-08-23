---
name: generate-video
description: Generate video with Kolbo.AI. Use when the user asks to create, generate, animate or render a video, clip, ad or motion piece — from a text prompt, from an existing image, or as a multi-scene sequence.
---

# Generate video with Kolbo

Three entry points, and picking the right one matters more than the prompt:

| The user has | Tool |
|---|---|
| Only an idea | `generate_video` (text to video) |
| A starting image | `generate_video_from_image` |
| A start and end frame | `generate_first_last_frame` |
| A whole scripted sequence | `generate_creative_director` |

Call `list_models` when the user cares about duration, resolution, sound or cost — video models differ sharply on all four, and durations are per-model rather than free-form.

## Rules that change the output

- **Sound**: some models generate native audio, others are silent. Check before promising a soundtrack.
- **Duration**: ask for a supported length rather than an arbitrary number, or the request is rejected.
- **Reference images** must be tagged in the prompt like images are: `@Kobi walks into frame`. Passing `visual_dna_ids` alone leaves the provider with nothing.
- **Text-to-video is not a Visual DNA image surface** — names and description only.

## Cost

Video is the most expensive thing in Kolbo. State the cost and get agreement before generating, especially for long clips or multi-scene batches. Use `get_generation_status` to poll; do not assume a job failed because it is slow.
