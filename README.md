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
| [`suno-lyrics-to-song`](skills/suno-lyrics-to-song) | [SKILL.md](skills/suno-lyrics-to-song/SKILL.md) | 0.2.3 |

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

## Updates

Each installed skill checks for a new version at most once a day, verifies the
official archive before replacing itself, and leaves your installation untouched
if anything fails. Turn it off at any time — see
`references/automatic-updates-and-safety.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.
