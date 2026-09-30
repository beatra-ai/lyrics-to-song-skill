# Lyrics to Song Skill

[English](./README.md) | 简体中文

把完整歌词、草稿或一句 hook 整理成结构清晰、可试听的歌曲，在 Claude Code、Codex 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 输入完整歌词、歌词草稿、零散歌词或一个 hook，整理主歌、副歌与桥段，设置曲风、情绪、编曲和人声方向，再用 Suno 自定义歌词生成可试听歌曲。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="歌曲《Taking the Light With Me》的封面：阳光洒进搬空的房间，地板上放着一只封好的纸箱。由 Beatra AI 生成。"></p>

*歌曲《Taking the Light With Me》的封面：阳光洒进搬空的房间，地板上放着一只封好的纸箱。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`suno-lyrics-to-song`](skills/suno-lyrics-to-song) | [SKILL.md](skills/suno-lyrics-to-song/SKILL.md) | 0.2.3 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/suno-lyrics-to-song) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/lyrics-to-song-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/lyrics-to-song-skill suno-lyrics-to-song
```

也可以克隆本仓库，把 `skills/suno-lyrics-to-song` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/lyrics-to-song-skill 安装 suno-lyrics-to-song skill（目录 skills/suno-lyrics-to-song），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="歌曲《Taking the Light With Me》的封面：阳光洒进搬空的房间，地板上放着一只封好的纸箱。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*原声民谣《Taking the Light With Me》前 60 秒，男声主唱，由一份零散歌词草稿整理成主歌、导歌、副歌和桥段后生成。由 Beatra AI 生成。*

提示词：

```text
Warm acoustic folk song about packing up an old apartment on moving day. Arc: quiet and wistful in the verses, opening into a warm, grateful sing-along chorus, a hushed near-whispered bridge, then a fuller final chorus that settles into a soft ending. Unhurried mid-slow tempo with a gentle swaying feel. Fingerpicked steel-string acoustic guitar, soft upright bass, brushed snare entering at the first chorus, warm upright piano, light cello swell on the choruses. Intimate close-miked male lead, plain-spoken conversational phrasing, soft harmony vocal on the final chorus. Natural room sound, analog warmth, uncluttered mix.
```

## 你能得到什么

- **重要的原词可以一字不改** — 可以完整保留每一行，也可以标记必须保留的句子，再用优化模式改善其余内容的节奏、押韵与可唱性。
- **把草稿整理成歌曲结构** — 让零散歌词进入主歌、副歌、桥段与有目的的重复，不强迫每份草稿套用同一个模板。
- **先确定成曲后的听感** — 在生成前明确风格、情绪、乐器、段落对比和演唱方式，让音乐方向与歌词表达一致。

## 适用场景

- **有完整歌词但还没有音乐** — 保留已经完成的歌词，为它建立清晰段落、情绪推进与演唱方向。
- **只有零散句和片段** — 把分散的歌词行整理成可唱顺序，同时保留原有含义和最有记忆点的意象。
- **已经有一句核心 hook** — 围绕已有 hook 建立段落对比和支撑内容，让歌曲身份更鲜明。
- **草稿需要改善演唱流畅度** — 在保护必留句的前提下，优化节奏、措辞、押韵、重复与段落平衡。

## 常见问题

### 可以从哪些歌词材料开始？

可以从完整歌词、零散草稿、几句歌词或已有 hook 开始。开始时至少需要一句已有歌词或一个已有 hook。

### 能完全保留我的原词吗？

可以。保留模式会让歌词正文中的每个字符、标点、完整歌词行及其先后顺序保持不变，只允许调整完整行周围的换行或空行，并在正文之外增加段落标签。

### 如何控制发音、人声方向和歌曲时长？

在音乐方向中明确语言、演唱方式、人声特征、歌曲结构和时长倾向，生成后试听完整表现，再把最重要的一处调整放进下一个版本。

### 试听后修改歌词会怎样？

修改歌词或音乐方向会生成一个新版本，也可能改变演唱和编曲，因此需要先检查更新后的完整歌词与方向。

## 更新

安装后的 skill 每天最多检查一次新版本，替换前先校验官方归档，任何一步失败都不会动你已安装的版本。
随时可以关闭，见 skill 内的 `references/automatic-updates-and-safety.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。
