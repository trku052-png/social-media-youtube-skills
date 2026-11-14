# Snapshot Limitations & Missing Supporting Files

This repository combines a curated set of upstream `SKILL.md` snapshots with three imported skill collections. Source files are preserved as supplied; this repository does not claim that every upstream project or package is complete.

## Curated upstream set

The 26 verified upstream entries under `skills/01-*` through `skills/26-*` were collected as `SKILL.md` snapshots. Several of those source instructions refer to scripts or references that were not included in the supplied snapshot. Examples include:

- `01-ffmpeg-skill`: `references/gotchas.md`
- `03-video-editing-workbench`: supporting files under `references/` (FFmpeg recipes, motion graphics, quality gates, render plan, timeline/compositing and workflow)
- `06-gemini-video-generation`: helper scripts under `scripts/`
- `09-analyze-video-editing`: audio/timing and editorial-analysis references
- `10-find-broll`: manifest/timing and sourcing/routing references
- `13-blender-previs-storyboard`: references and `scripts/bx_previs.py`
- `14-caption-styling`: FFmpeg burn-in and platform safe-zone references
- `15-audio-ducking`: FFmpeg recipe references
- `17-photoshop-expert`: `references/07-standards.md`
- `19-media-studio`: `references/salvage-and-enhancement.md`
- `20-filmcraft-expert`: linked `video-editor` and `ffmpeg` skill folders
- `21-cli-anything-video-creation`: CLI matrix schema, references and `scripts/video_doctor.py`

Archived upstream snapshots under `skills/upstream/` contain similar missing references because they are retained as historical skill-file copies, not full source checkouts.

## Imported collection packages

The following package references were found in the supplied archives but are not present as local files:

- `collections/motion-design-adobe/video-editing`: `assets/fusion/ito-production-v1/README.md` and `assets/fusion/ito-v28/README.md`
- `collections/social-media-youtube/webinar-content-and-events`: `references/repurposing-templates.md`
- `collections/social-media-youtube/ph-content-recycling`: `gallery-image-1.png`
- `collections/social-media-youtube/social-media-setup`: `references/reusable-prompt.md`, `references/common-pitfalls.md`, `references/related-skills.md` and `references/security-safety-notes.md`

Some skill files also contain example URLs or template placeholders that are not repository-relative files; those are not classified as missing local dependencies here.

## Recommended action

Before running a skill, open its `SKILL.md`, check its prerequisites, and follow its exact upstream link in [UPSTREAM_SOURCES.md](UPSTREAM_SOURCES.md) where available. Obtain missing references or scripts from the matching source revision rather than guessing or substituting files from a different version.
