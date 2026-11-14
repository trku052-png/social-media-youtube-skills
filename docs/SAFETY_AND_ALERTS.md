# Safety, Permissions and Production Alerts

This library includes skills that can interact with local files, APIs, social networks, cloud platforms, Adobe applications, creative models and external media sources. Use the following control gates.

## Permission levels
- **Read-only:** inspect, research, summarize, analyze, compare, transcribe.
- **Local write:** create or alter files, exports, project files and rendered media. Work on copies and make backups.
- **External side effect:** publish, send, schedule, delete, buy, change account settings, invite users or expose private assets. Require an explicit human approval immediately before the action.

## High-priority alerts
1. **Credentials:** never commit keys, tokens, cookies, passwords, private certificates or credential files.
2. **Social publishing:** check account, destination, copy, media, tags, visibility and time before posting.
3. **Media rights:** verify permission for music, SFX, fonts, stock footage, photographs, voices, likenesses and datasets.
4. **Privacy:** remove private user data from transcripts, screenshots, analytics exports and generated samples.
5. **Destructive editing:** preserve source footage and project files; use non-destructive edits where possible.
6. **AI outputs:** review factual claims, artifacts, audio pronunciation, captions, visual defects and model-specific restrictions.
7. **Quality control:** verify duration, dimensions, aspect ratio, frame rate, codec, bitrate, loudness, black frames and subtitle timing.
8. **Platform changes:** check current platform policies, upload limits, API behavior and supported formats before a production release.

## Stop conditions
Pause the workflow when a required dependency is missing, a tool permission is unclear, a source asset's provenance is unknown, an API action could affect the wrong account, or an output fails quality checks. Do not silently guess.
