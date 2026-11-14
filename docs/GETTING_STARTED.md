# Getting Started

## What is an Agent Skill?

An Agent Skill is a directory of instructions and, where supplied, supporting resources that tells a compatible AI agent how to approach a specific task. The core entry point is usually `SKILL.md`. Some packages also include scripts, references, templates, examples or evaluation cases.

## Choose a skill

Browse the [complete catalog](SKILL_CATALOG.md). Search by task (for example, `youtube-shorts`, `audio-mixing-mastering`, `after-effects` or `content-calendar-and-repurposing`) and open the exact path shown in the catalog. Similar names may refer to different versions or providers; compare the full path and requirements.

## Installation

Installation depends on the agent or host application. Do not assume that copying a folder into one agent automatically installs it in another. Follow the compatible agent's current official skill-loading documentation. A typical local workflow is:

1. Clone or download this repository.
2. Copy the selected skill directory into the skills location supported by your agent.
3. Keep the full directory, including references and scripts that the skill expects.
4. Read the entire `SKILL.md` and check its `compatibility`, `allowed-tools`, `license` and metadata fields.
5. Configure any required local software, API credentials or MCP servers outside the repository.
6. Test with non-sensitive sample material before using production media or connected accounts.

## Source snapshots and missing support files

Some curated upstream entries intentionally preserve only the verified `SKILL.md` file, not every upstream script or reference. A skill may therefore contain relative links to files that are not present in this repository. Use [the upstream source bibliography](UPSTREAM_SOURCES.md) to locate the exact upstream repository and recorded commit before attempting the workflow. A few imported archives may also omit optional assets or examples.

## Common requirements

Depending on the package, you may need Python, Node.js, FFmpeg/ffprobe, Blender, Adobe Creative Cloud applications, a local editor, model weights, internet access, an API key, a paid subscription or an MCP server. Requirements are skill-specific; check the package itself.

## Compatibility and limitations

- A skill is not necessarily compatible with every agent runtime.
- Some packages refer to scripts, references or tools that are not included in every source archive.
- Cloud APIs may incur fees, enforce quotas or change their terms.
- A connected tool may have permissions that differ from the instruction package.
- AI output still requires human review for factual accuracy, creative quality, rights and platform compliance.

## Publishing safety

Never place API keys, access tokens, passwords, cookies or private user data in this repository. Require explicit human approval before any agent posts, schedules, sends, deletes or changes a connected account.
