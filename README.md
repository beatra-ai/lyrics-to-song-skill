# Lyrics to Song Skill

English | [简体中文](./README.zh-CN.md)

Turn full lyrics, a rough draft, or a hook into a structured song with clear sections, style, and vocal direction, from inside Claude Code, Codex, or OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Turn complete lyrics, rough drafts, loose lines, or a hook into a structured Suno song with custom lyrics, clear sections, style, mood, arrangement, and vocal direction. |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Codex, OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="Cover art for &quot;Taking the Light With Me&quot;, a folk song about moving out of an old apartment, showing one taped box in an empty sunlit room. AI-generated with Beatra."></p>

*Cover art for "Taking the Light With Me", a folk song about moving out of an old apartment, showing one taped box in an empty sunlit room. AI-generated with Beatra.*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`suno-lyrics-to-song`](skills/suno-lyrics-to-song) | [SKILL.md](skills/suno-lyrics-to-song/SKILL.md) | 0.2.7 |

This repository is published automatically from [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/suno-lyrics-to-song). Report issues there.

## Install

With the [`skills`](https://skills.sh) CLI:

```bash
npx skills add beatra-ai/lyrics-to-song-skill
```

With the GitHub CLI:

```bash
gh skill install beatra-ai/lyrics-to-song-skill suno-lyrics-to-song
```

Or clone this repository and copy `skills/suno-lyrics-to-song` into `~/.claude/skills/` for Claude Code,
`~/.agents/skills/` for Codex, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the suno-lyrics-to-song skill from https://github.com/beatra-ai/lyrics-to-song-skill (folder skills/suno-lyrics-to-song), then follow its SKILL.md to connect my Beatra account.
```

## Examples

<p align="center"><img src="assets/cover.webp" width="800" alt="Cover art for &quot;Taking the Light With Me&quot;, a folk song about moving out of an old apartment, showing one taped box in an empty sunlit room. AI-generated with Beatra."></p>

[▶ Listen (MP3)](assets/sample.mp3)

*First 60 seconds of "Taking the Light With Me", an acoustic folk song with a male lead, made by structuring a rough lyric draft into verse, pre-chorus, chorus and bridge. AI-generated with Beatra.*

Prompt:

```text
Warm acoustic folk song about packing up an old apartment on moving day. Arc: quiet and wistful in the verses, opening into a warm, grateful sing-along chorus, a hushed near-whispered bridge, then a fuller final chorus that settles into a soft ending. Unhurried mid-slow tempo with a gentle swaying feel. Fingerpicked steel-string acoustic guitar, soft upright bass, brushed snare entering at the first chorus, warm upright piano, light cello swell on the choruses. Intimate close-miked male lead, plain-spoken conversational phrasing, soft harmony vocal on the final chorus. Natural room sound, analog warmth, uncluttered mix.
```

## Technical Specifications & Output Limits

As of 2026-10-16. Live list: https://docs.beatra.ai/en/docs/models

- **Uploads** — up to 100 MB per file; the per-model input limits below also apply
- **Text to music** — 2 models (Suno 6, MiniMax Music 3.0); MP3
  - Suno 6: prompt up to 500, lyrics up to 5000, title up to 80 characters
  - MiniMax Music 3.0: prompt up to 2000, lyrics up to 3500, title up to 100 characters
- **Reference audio to music** — 2 models (Suno 6, MiniMax Music 3.0); MP3
  - Suno 6: prompt up to 500, lyrics up to 5000, title up to 80 characters; reference audio 6–480 s (FLAC, MP3, WAV)
  - MiniMax Music 3.0: prompt up to 300, lyrics up to 1000, title up to 100 characters; reference audio 6–360 s, up to 50 MB (FLAC, MP3, WAV)

## Why use Beatra instead of calling model APIs directly

- **One account for every model this skill uses** — Text to music 2; Reference audio to music 2 (as of 2026-10-16), behind one Beatra sign-in; no keys from individual model providers to manage.
- **You decide what gets paid for** — Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate.
- **Direction before rendering** — the skill plans, directs, and reviews the work, then renders it on Beatra.
- **Files you can verify** — every file under `skills/` matches the release archive on cdn.beatra.ai byte for byte, checked by SHA-256 before each push.
- **Updates you control** — no self-updater; update with the tool you installed it with.
- **Runs in your agent** — Claude Code, Codex, OpenClaw.

## How it compares

| | Beatra (this skill) | [regiellis/suno-songwriter-agent-skill](https://github.com/regiellis/suno-songwriter-agent-skill) | [scenario-labs/skills](https://github.com/scenario-labs/skills) |
| --- | --- | --- | --- |
| Account or key needed | A Beatra account; no model provider keys | Lists no account or key; it writes song packages for Suno v6 Simple or Advanced mode ([source](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/README.md#L6-L17)) | A Scenario account (OAuth) or a Scenario API key ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L105)) |
| Models | Text to music 2; Reference audio to music 2 | Writes for Suno v6, v6-wild and v6-mini ([source](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/README.md#L26)) | Vocal songs from a tagged lyric sheet (MiniMax music), plus ACE-Step and ElevenLabs music ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L285-L287)) |
| Before spending | Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate | Not stated | Dry-run price estimates in its quality-gate and model-comparison skills ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L208-L210)) |
| Agents | Claude Code, Codex, OpenClaw | Any harness that reads SKILL.md, including Claude Desktop and Codex Desktop ([source](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/README.md#L8-L133)) | Claude Code, Cursor, Codex, Copilot and 70+ others ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L30)) |
| Install | `npx skills add beatra-ai/lyrics-to-song-skill` | Download the skill ZIP from its documentation site ([source](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/README.md#L116)) | `npx skills add scenario-labs/skills`, then connect the Scenario MCP server (https://mcp.scenario.com/mcp) ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L89-L105)) |
| License | MIT-0 | MIT ([source](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/LICENSE)) | MIT ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/LICENSE)) |
| Last updated | Updated with every release (v0.2.7) | 2026-10-11 ([source](https://github.com/regiellis/suno-songwriter-agent-skill/commit/cc3053bd027f822476734f41edbf9ae98078f61a)) | 2026-10-15 ([source](https://github.com/scenario-labs/skills/commit/49dd26e47371163ae0020c7f5627d0993626bfc2)) |

Facts checked on 2026-10-16. Corrections: open an issue in [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/issues).

## What you get

- **Keep the words that matter** — Preserve every original line, or mark the must-keep phrases and refine the remaining lyrics for stronger flow and singability.
- **Build a song-shaped structure** — Arrange loose material into verses, chorus, bridge, and purposeful repetition without forcing every draft into the same template.
- **Define how the track should feel** — Choose style, mood, instrumentation, section contrast, and vocal delivery before creating a listenable version.

## Use cases

- **Complete lyrics without music** — Keep a finished lyric intact while giving it a coherent section order, musical arc, and vocal direction.
- **Loose lines and fragments** — Sort scattered lyric lines into a singable sequence while preserving their meaning and strongest images.
- **An existing hook** — Build contrast and supporting sections around a hook that already carries the song's identity.
- **A draft that needs better flow** — Refine rhythm, phrasing, rhyme, repetition, and section balance while protecting every must-keep line.

## FAQ

### What lyric material can I start with?

You can start with complete lyrics, a rough draft, loose lyric lines, or an existing hook. At least one existing lyric line or hook is needed to begin.

### Can my original lyrics stay exactly as written?

Yes. Preserve mode keeps every lyric-body character, punctuation mark, complete line, and the exact line order unchanged. Only surrounding line breaks or blank-line spacing may be adjusted, and section labels may be added outside the lyric body.

### How are pronunciation, vocal direction, and track length shaped?

Set the language, delivery, vocal character, song structure, and duration direction in the brief, then listen to the finished performance and refine the most important detail in the next version.

### What happens if I change the lyrics after hearing the track?

A lyric or direction change creates a new version and may also change the vocal performance and arrangement, so review the complete updated words and direction before creating it.

## Updates and security

Since the 2026-10 release, this skill contains no self-updater: it runs only the
files you installed and never replaces them on its own. Update it with the tool
you installed it with — `npx skills update suno-lyrics-to-song` or `gh skill update suno-lyrics-to-song`.
Details: `references/updates-and-security.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.

## Links

- Website — https://beatra.ai
- Docs — https://docs.beatra.ai
- Console — https://console.beatra.ai
- For AI agents — https://beatra.ai/llms.txt (index) · https://beatra.ai/llms-full.txt (every skill in one file)
