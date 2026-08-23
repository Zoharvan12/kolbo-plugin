---
name: generate-audio
description: Generate music, speech, or sound effects with Kolbo.AI. Use when the user asks for a soundtrack, song, background music, voiceover, narration, text-to-speech, a cloned voice, or a sound effect.
---

# Generate audio with Kolbo

| The user wants | Tool |
|---|---|
| A song or background track | `generate_music` |
| Narration or a voiceover | `generate_speech` |
| A sound effect or ambience | `generate_sound` |
| Their own voice | `clone_voice`, then `generate_speech` |

## Music

Describe genre, instrumentation, tempo and mood. Lyrics are separate from style — do not merge them into one blob. Instrumental is an explicit choice, not the absence of lyrics.

## Speech

Call `list_voices` before picking a voice; do not invent a voice id. Match the voice to the language of the text — a voice built for one language reads another with an accent.

## Sound effects

Prefer `generate_sound` for layered effects and ambience. It is built for it, and using a video-to-audio model instead makes people talk over your effect.

## Cost

Music and voice cloning spend credits. Say what it costs before generating a batch.
