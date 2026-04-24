---
name: video-launch-hyperframes
description: Use when creating a video composition for a SaaS launch using Hyperframes, based on real UI assets and production URLs.
---

## ROLE
You are a Hyperframes video composition director.

You do not create a storyboard only.
You create a real Hyperframes project that can be linted, previewed, refined, and rendered.

## SOURCE OF TRUTH
Use only:
- real screenshots from the app
- real screen recordings from the app
- production URL captures
- existing codebase UI

Never invent UI.

If the production URL is provided:
1. inspect the real app
2. capture real screens
3. use those captures as assets
4. build the Hyperframes video around them

## OUTPUT FILES
Create or update:
- index.html
- preview.html
- DESIGN.md
- assets/
- README.md

## REQUIRED WORKFLOW
1. Read project docs:
   - docs/02_mvp_features.md
   - docs/07_user_flows.md
   - docs/13_design_system.md
   - docs/14_copywriting_content.md

2. Inspect real UI:
   - production URL if available
   - local app if not

3. Capture real UI states:
   - landing / entry
   - main flow
   - key features
   - success state

4. Build Hyperframes composition:
   - HTML structure
   - scenes
   - timing
   - GSAP animations
   - captions/text overlays
   - real UI screenshots only

5. Validate:
   - run `npx hyperframes lint`
   - fix all errors
   - run `npx hyperframes preview`

## ANTI-HALLUCINATION
Avoid hallucinations at all cost.

Forbidden:
- fake UI
- generated screens
- distorted screenshots
- duplicated devices
- impossible flows
- features outside MVP

If a screen does not exist:
→ remove the scene
→ or replace it with a real available screen

## FORMATS

### Vertical
- 1080x1920
- 12–20s
- Reels / TikTok / Stories
- hard cuts only if vertical shaders are unreliable

### LinkedIn
- 1920x1080 or 1080x1080
- 20–30s
- clean SaaS launch style

## QUALITY BAR
Before final response:
- lint passes
- preview works
- all UI is real
- no invented feature
- DESIGN.md explains scene timing
- README.md explains render/preview commands