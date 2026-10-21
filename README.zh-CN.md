# Lyrics to Song Skill

[English](./README.md) | 简体中文 | [日本語](./README.ja.md)

> 👉 也看看 [AI Music Generator Skill](https://github.com/beatra-ai/ai-music-generator-skill)

把完整歌词、草稿或一句 hook 整理成结构清晰、可试听的歌曲，在 Claude Code、Cursor、Codex、Windsurf、Cline 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=lyrics-to-song-skill) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 输入完整歌词、歌词草稿、零散歌词或一个 hook，整理主歌、副歌与桥段，设置曲风、情绪、编曲和人声方向，再用 Suno 自定义歌词生成可试听歌曲。 |
| **底层模型** | Suno 6、MiniMax Music 3.0 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="歌曲《Taking the Light With Me》的封面：阳光洒进搬空的房间，地板上放着一只封好的纸箱。由 Beatra AI 生成。"></p>

*歌曲《Taking the Light With Me》的封面：阳光洒进搬空的房间，地板上放着一只封好的纸箱。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`suno-lyrics-to-song`](skills/suno-lyrics-to-song) | [SKILL.md](skills/suno-lyrics-to-song/SKILL.md) | 0.3.0 |

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

也可以克隆本仓库，把 `skills/suno-lyrics-to-song` 复制到 `~/.claude/skills/`（Claude Code）、`~/.cursor/skills/`（Cursor）、`~/.agents/skills/`（Codex）、`~/.codeium/windsurf/skills/`（Windsurf）、`~/.cline/skills/`（Cline）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/lyrics-to-song-skill 安装 suno-lyrics-to-song skill（目录 skills/suno-lyrics-to-song），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="歌曲《Taking the Light With Me》的封面：阳光洒进搬空的房间，地板上放着一只封好的纸箱。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*原声民谣《Taking the Light With Me》前 60 秒，男声主唱，由一份零散歌词草稿整理成主歌、导歌、副歌和桥段后生成。由 Beatra AI 生成。*

在你的 Agent 里这样说：

```text
这是我写的一段粗糙歌词，讲搬家那天收拾旧公寓（在 ./lyrics.txt 里）。帮我整理成主歌、预副歌、副歌和桥段，做成一首温暖的男声原声民谣。
```

提示词：

```text
Warm acoustic folk song about packing up an old apartment on moving day. Arc: quiet and wistful in the verses, opening into a warm, grateful sing-along chorus, a hushed near-whispered bridge, then a fuller final chorus that settles into a soft ending. Unhurried mid-slow tempo with a gentle swaying feel. Fingerpicked steel-string acoustic guitar, soft upright bass, brushed snare entering at the first chorus, warm upright piano, light cello swell on the choruses. Intimate close-miked male lead, plain-spoken conversational phrasing, soft harmony vocal on the final chorus. Natural room sound, analog warmth, uncluttered mix.
```

## 技术规格与输出限制

截至 2026-10-18。实时列表：https://docs.beatra.ai/zh/docs/models

- **上传** — 单个文件最大 100 MB；同时适用下方各模型的输入限制
- **文生音乐** — 2 个模型（Suno 6、MiniMax Music 3.0）；MP3
  - Suno 6：提示词最多 500、歌词最多 5000、标题最多 80 字符
  - MiniMax Music 3.0：提示词最多 2000、歌词最多 3500、标题最多 100 字符
- **参考音频生音乐** — 2 个模型（Suno 6、MiniMax Music 3.0）；MP3
  - Suno 6：提示词最多 500、歌词最多 5000、标题最多 80 字符；参考音频 6–480 秒（FLAC、MP3、WAV）
  - MiniMax Music 3.0：提示词最多 300、歌词最多 1000、标题最多 100 字符；参考音频 6–360 秒，最大 50 MB（FLAC、MP3、WAV）

## 为什么用 Beatra，而不是直接调用模型 API

- **一个账号用到本 skill 的全部模型** — 文生音乐 2；参考音频生音乐 2（Suno 6、MiniMax Music 3.0）（截至 2026-10-18），一次 Beatra 登录即可使用，不必分别管理各家模型的 key。
- **花不花钱由你决定** — 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费。
- **先策划，再生成** — skill 先帮你规划、指导和检查，再在 Beatra 上生成。
- **文件可以核验** — `skills/` 下的每个文件都与 cdn.beatra.ai 上的发布归档逐字节一致，每次推送前用 SHA-256 校验。
- **更新由你掌控** — 不含自更新程序；用安装时的工具更新。
- **在你的 Agent 里运行** — Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw。

## 与同类方案对比

| | Beatra（本 skill） | [regiellis/suno-songwriter-agent-skill](https://github.com/regiellis/suno-songwriter-agent-skill) | [scenario-labs/skills](https://github.com/scenario-labs/skills) |
| --- | --- | --- | --- |
| 需要的账号或 key | 一个 Beatra 账号，不需要各家模型的 key | 未列出需要的账号或 key；它写出供 Suno v6 简单或高级模式使用的歌曲包（[出处](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/README.md#L6-L17)） | Scenario 账号（OAuth 登录）或 Scenario API key（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L105)） |
| 模型 | 文生音乐 2；参考音频生音乐 2（Suno 6、MiniMax Music 3.0） | 面向 Suno v6、v6-wild 和 v6-mini 编写（[出处](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/README.md#L26)） | 按带标签的歌词单生成人声歌曲（MiniMax 音乐），另有 ACE-Step 和 ElevenLabs 音乐（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L285-L287)） |
| 花钱前 | 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费 | 未说明 | 质量检查和模型对比两个 skill 可先 dry-run 试算价格（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L208-L210)） |
| 支持的 Agent | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw | 任何能读取 SKILL.md 的 Agent，包括 Claude Desktop 和 Codex Desktop（[出处](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/README.md#L8-L133)） | Claude Code、Cursor、Codex、Copilot 及另外 70 多种编程 Agent（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L30)） |
| 安装 | `npx skills add beatra-ai/lyrics-to-song-skill` | 从它的文档站下载 skill ZIP（[出处](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/README.md#L116)） | `npx skills add scenario-labs/skills`，再连接 Scenario MCP 服务器（https://mcp.scenario.com/mcp）（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L89-L105)） |
| 许可证 | MIT-0 | MIT（[出处](https://github.com/regiellis/suno-songwriter-agent-skill/blob/cc3053bd027f822476734f41edbf9ae98078f61a/LICENSE)） | MIT（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/LICENSE)） |
| 最近更新 | 随每次发布更新（v0.3.0） | 2026-10-11（[出处](https://github.com/regiellis/suno-songwriter-agent-skill/commit/cc3053bd027f822476734f41edbf9ae98078f61a)） | 2026-10-15（[出处](https://github.com/scenario-labs/skills/commit/49dd26e47371163ae0020c7f5627d0993626bfc2)） |

事实核对于 2026-10-16。有误请到 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/issues) 提 issue。

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

## 更新与安全

自 2026 年 10 月的版本起，本 skill 不再包含自更新程序：它只运行你安装的文件，从不自行替换。
请用安装时的工具更新——`npx skills update suno-lyrics-to-song` 或 `gh skill update suno-lyrics-to-song`。
详见 skill 内的 `references/updates-and-security.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。

## 相关链接

- 官网 — https://www.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=lyrics-to-song-skill
- 文档 — https://docs.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=lyrics-to-song-skill
- 控制台 — https://console.beatra.cn
- 给 AI Agent 读的说明 — https://www.beatra.cn/llms.txt（索引）· https://www.beatra.cn/llms-full.txt（全部 skill 合成一个文件）

- 微信小程序 — 国内用户微信扫码使用

<img src="assets/beatra-mini-program-qr.jpg" alt="Beatra 微信小程序码" width="160">
