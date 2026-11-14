# Usage Guide — Find, Read, Install and Operate a Skill

## 1. Find the right skill
Start in [the complete skill catalog](SKILL_CATALOG.md). Search by task or tool, not only by package name. When names overlap, use the full path and collection to choose the correct version.

## 2. Inspect the complete package
Open the selected `SKILL.md`. Then inspect any `references/`, `scripts/`, `assets/`, `templates/`, `examples/` or `evals/` directories next to it. Do not copy only the instruction file when it expects sibling support files.

## 3. Check prerequisites
Look for required runtimes, command-line utilities, applications, API credentials, MCP servers, network access, subscriptions, model access and local input files. The package may be only an instruction layer, not an executable application.

## 4. Install for your agent
Use the current installation method supported by your particular agent runtime. Skill-loading conventions vary. Keep the directory name and internal relative paths intact, and do not assume that a package installed in one agent is also installed in another.

## 5. Run a safe test
Test on copies or synthetic sample media first. Confirm output path, codec, aspect ratio, resolution, frame rate, audio level, subtitles, metadata and licensing constraints as relevant.

## 6. Review before publishing
Human approval is required before external actions such as posting, scheduling, sending, deleting files, or modifying connected accounts. Check every final export and platform-specific requirement yourself.

## Typical workflow
`Research → Brief → Script/Storyboard → Production → Edit → Audio/Caption QC → Export → Publish → Measure → Iterate`

## Common warnings
- Keep API keys and tokens outside the repository and out of prompts, logs and screenshots.
- Never assume a music, font, footage, stock image, model or template is cleared for every use.
- Do not automate a platform action simply because an instruction file describes it; check the actual connected tool and permission.
- Do not trust generated analytics or trend claims without evidence and a timestamp.
- Make backups before batch editing or transcoding original media.
