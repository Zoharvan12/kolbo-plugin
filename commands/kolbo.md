---
description: Run Kolbo workflows in natural language — generate images, video, music and voice, manage projects and media, check credits.
---

Use the Kolbo MCP tools to carry out the user's request: $ARGUMENTS

Load the bundled `kolbo` skill first and follow its routing index and approval
rules. Micro-drama series use `references/workflows/micro-drama.md` inside that
skill. The canonical skill takes precedence over the quick-start notes below.

Guidance:
- Resolve the target project once with `list_projects`, then pass the same `project_id` on every later call.
- Tag every Visual DNA in the prompt text as `@Name` and every moodboard as `#Name`, in addition to passing their ids.
- Call `list_models` rather than guessing a model identifier.
- Generation spends credits — state the cost before anything large, and use `check_credits` if the user asks about balance.
- Deliver the finished media. Do not describe what you would have made.
