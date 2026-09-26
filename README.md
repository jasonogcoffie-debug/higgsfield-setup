# Higgsfield setup

Higgsfield AI agent skills from [higgsfield-ai/skills](https://github.com/higgsfield-ai/skills), installed with:

```
npx skills add higgsfield-ai/skills
```

Skills live in `.agents/skills/` (shared by all agents) and are symlinked into `.claude/skills/` for Claude Code. `skills-lock.json` pins the installed versions; refresh with `npx skills update`.

## Prerequisites

- Higgsfield CLI on `PATH`, logged in:
  ```
  higgsfield auth login
  higgsfield account status
  ```
- **Windows:** git checks symlinks out as plain text files unless Developer Mode is on and `git config core.symlinks true` is set. If `.claude/skills/*` shows up as one-line files, re-run `npx skills add higgsfield-ai/skills` in the clone (or `-g` to install for all projects).

## Using the skills from Claude

Just ask in plain language — Claude picks the skill from the request. You can also invoke one directly, e.g. `/higgsfield-generate`.

| Skill | Use it for |
|---|---|
| `higgsfield-generate` | Images, videos, image-to-video, edits, 3D, audio, ads/UGC |
| `higgsfield-product-photoshoot` | Product/brand photos, lifestyle shots, ad creatives |
| `higgsfield-marketplace-cards` | Marketplace listing images and A+ modules |
| `higgsfield-soul-id` | Train a reusable face model (Soul) for consistent characters |
| `higgsfield-video-explainer` | Narrated, animated explainer videos |
| `higgsfield-youtube-thumbnail` | YouTube thumbnails and Shorts covers |
| `higgsfield-brandkit` | Logos, palettes, brandbooks, branded mockups |
| `higgsfield-websites` | Build and deploy sites, apps, games |

Example prompts:

- "Generate a 16:9 image of a neon-lit Tokyo street in the rain."
- "Animate this photo into a 5-second video with a slow push-in." (attach the image)
- "Make a 9:16 product video of my sneaker spinning on a pedestal."
- "Train my Soul from these 10 photos, then put me in a cinematic desert scene."
- "What would this cost?" — Claude can check credits before generating.

Defaults: GPT Image 2.5 for images, Seedance 2.5 for video. Name a model or aspect ratio to override.

## Equivalent CLI commands

```
higgsfield model list
higgsfield generate create gpt_image_2_5 --prompt "..." --aspect_ratio 1:1 --wait
higgsfield generate create seedance_2_5 --prompt "..." --wait
higgsfield workflow list
```
