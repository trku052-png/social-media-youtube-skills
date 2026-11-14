# Snapshot Limitations & Missing Supporting Files

The 26 curated upstream entries under `skills/01-*` through `skills/26-*` were collected primarily as `SKILL.md` snapshots. Several source instructions refer to scripts or references that were not included in the supplied snapshot.

Examples include:

- `01-ffmpeg-skill`: `references/gotchas.md`
- `03-video-editing-workbench`: supporting files under `references/`
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

Archived upstream snapshots may have the same gaps because they preserve earlier skill-file copies, not complete source checkouts.

Before running a skill, inspect its complete instruction file and follow its upstream source. The 26-skill source repositories and recorded file-level commit references are included in [manifest-verified-26.json](../manifest-verified-26.json).
