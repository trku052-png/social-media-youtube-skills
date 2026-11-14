# Getting Started

## What is an Agent Skill?

An Agent Skill is a directory of instructions and, where supplied, supporting resources that tells a compatible AI agent how to approach a specific task. The usual entry point is `SKILL.md`. Some packages also include scripts, references, templates, examples or evaluation cases.

## Choose a skill

Browse the [Skill Catalog](SKILL_CATALOG.md). Search by task, then open the exact file path. Similar names may refer to different versions or providers, so compare the source and requirements.

## Installation

Installation depends on the agent or host application. Do not assume that copying a folder into one agent automatically installs it in another. Follow the compatible agent's current official skill-loading documentation. A typical workflow is:

1. Clone or download this repository.
2. Copy the selected skill directory into the skills location supported by your agent.
3. Keep the full directory, including references and scripts the skill expects.
4. Read the entire `SKILL.md` and check its compatibility, allowed tools, license and metadata.
5. Configure required local software, API credentials or MCP servers outside the repository.
6. Test with non-sensitive sample material before using production media or connected accounts.

## Common requirements

Depending on the package, you may need Python, Node.js, FFmpeg/ffprobe, Blender, Adobe Creative Cloud applications, a local editor, model weights, internet access, an API key, a paid subscription or an MCP server. Requirements are skill-specific; check the package itself.

## Source snapshots and missing support files

Some curated upstream entries preserve only the verified `SKILL.md` file, not every upstream script or reference. A skill may therefore refer to support files that are not present in this repository. Check [Snapshot Limitations](SNAPSHOT_LIMITATIONS.md) and the corresponding upstream repository before attempting that workflow. Obtain missing files from the matching source revision rather than guessing or substituting from another version.

## Compatibility and limitations

- A skill is not necessarily compatible with every agent runtime.
- Cloud APIs may incur fees, enforce quotas or change their terms.
- A connected tool may have permissions that differ from the instruction package.
- AI output still requires human review for factual accuracy, creative quality, rights and platform compliance.

## Publishing safety

Never place API keys, access tokens, passwords, cookies or private user data in this repository. Require explicit human approval before an agent posts, schedules, sends, deletes or changes a connected account.
