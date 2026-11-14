# Third-Party Notices

This repository contains project-authored material and imported skill packages. The imported material retains its own licensing and attribution requirements.

## Curated upstream video and creative set

The 26 documented upstream skills are listed in [INDEX-26.md](INDEX-26.md), with file-level repository links, commit hashes and source-license notes in [UPSTREAM_SOURCES.md](docs/UPSTREAM_SOURCES.md). Copies of the upstream licenses that were included are retained under `licenses/upstream/` and `third_party/`.

Important findings from that review:

- The 26-skill research snapshot records MIT and Apache-2.0 source projects, plus skill-text or additional attribution requirements for specific files.
- `caption-styling` and `audio-ducking` declare CC-BY-4.0 for skill text in their frontmatter; code/scripts may have a separate license.
- `video-editagent` had no root LICENSE in the inspected source snapshot. Treat its redistribution status as unverified.
- Separate fonts, footage, models, plugins, music, images and other embedded assets may have their own terms.

## Additional user-supplied collections

The following imported archives were unpacked into `collections/` while retaining each package's supplied `SKILL.md` and included support files:

- `social-media-youtube-skills.zip` → `collections/social-media-youtube-starter/` (13 packages)
- `social-media-youtube-skills-all.zip` → `collections/social-media-youtube/` (89 packages)
- `audio-sfx-video-libraries-skills.zip` → `collections/audio-video-production/` (94 packages)
- `video-motion-adobe-skills.zip` → `collections/motion-design-adobe/` (64 packages)

For these imported packages, license information is recorded from the supplied `SKILL.md` frontmatter and any included package-level license files. Some packages do not state a license in the supplied archive. This does not establish that they are public domain or freely reusable. See [Licensing & Provenance](docs/LICENSING.md) and the exact package paths in [the catalog](docs/SKILL_CATALOG.md).

## Original project skills

The 13 original social-media and YouTube skill files from the starter pack are retained under `skills/`. The standalone 13-skill zip was not duplicated because its content matches the 13 project skills already present in the main archive.

## Attribution and reuse

Do not remove upstream copyright notices. Where an imported package does not include a clear source or license, verify the terms with its original author or repository before redistributing or using it commercially. The root `LICENSE` is limited to project-authored material and does not override any third-party license.
