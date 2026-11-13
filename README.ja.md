# Lyrics to Song Skill

[English](./README.md) | [简体中文](./README.zh-CN.md) | 日本語

> 👉 こちらもどうぞ [AI Music Generator Skill](https://github.com/beatra-ai/ai-music-generator-skill)

完成した歌詞、下書き、フックを、構成・スタイル・ボーカルの方向が定まった 1 曲に。Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw のどれからでもそのまま使えます。

> [!IMPORTANT]
> 生成には [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=lyrics-to-song-skill) アカウントが必要で、クレジットを消費します。スキル自体のインストールは無料です。

| 項目 | 内容 |
| --- | --- |
| **できること** | 完成した歌詞、下書き、断片的なフレーズ、またはフックを構成し、Sunoカスタム歌詞で試聴できる曲に仕上げます。 |
| **モデル** | Suno 6、MiniMax Music 3.0 |
| **動作要件** | Python 3.10 以上と、`SKILL.md` を読み込めるエージェント |
| **費用** | インストールは無料。生成のたびに Beatra アカウントのクレジットを消費しますが、課金されるのは、その生成を明示的に依頼したとき、または確認カードを承認したときだけです。 |
| **対応エージェント** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="古いアパートから引っ越す歌「Taking the Light With Me」のカバーアート。日の差す空き部屋にテープで閉じた箱が 1 つ。Beatra AI で生成。"></p>

*古いアパートから引っ越す歌「Taking the Light With Me」のカバーアート。日の差す空き部屋にテープで閉じた箱が 1 つ。Beatra AI で生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`suno-lyrics-to-song`](skills/suno-lyrics-to-song) | [SKILL.md](skills/suno-lyrics-to-song/SKILL.md) | 0.3.3 |

このリポジトリは [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/suno-lyrics-to-song) から自動的に公開されています。問題の報告はそちらへお願いします。

## インストール

[`skills`](https://skills.sh) CLI を使う場合：

```bash
npx skills add beatra-ai/lyrics-to-song-skill
```

Claude Code プラグインとして：

```bash
claude plugin marketplace add beatra-ai/lyrics-to-song-skill
claude plugin install suno-lyrics-to-song@lyrics-to-song-skill
```

Codex プラグインとして：

```bash
codex plugin marketplace add beatra-ai/lyrics-to-song-skill
codex plugin add suno-lyrics-to-song@lyrics-to-song-skill
```

GitHub Copilot CLI プラグインとして：

```bash
copilot plugin marketplace add beatra-ai/lyrics-to-song-skill
copilot plugin install suno-lyrics-to-song@lyrics-to-song-skill
```

Gemini CLI 拡張機能として：

```bash
gemini extensions install https://github.com/beatra-ai/lyrics-to-song-skill
```

Antigravity CLI プラグインとして：

```bash
agy plugin install https://github.com/beatra-ai/lyrics-to-song-skill
```

GitHub CLI を使う場合：

```bash
gh skill install beatra-ai/lyrics-to-song-skill suno-lyrics-to-song
```

または、このリポジトリをクローンして `skills/suno-lyrics-to-song` を次の場所にコピーします：Claude Code は `~/.claude/skills/`、Cursor は `~/.cursor/skills/`、Codex は `~/.agents/skills/`、Windsurf は `~/.codeium/windsurf/skills/`、Cline は `~/.cline/skills/`、OpenClaw は `~/.openclaw/skills/`。

または、次の文をエージェントに貼り付けてください：

```text
https://github.com/beatra-ai/lyrics-to-song-skill から suno-lyrics-to-song スキル（フォルダ skills/suno-lyrics-to-song）をインストールし、その SKILL.md に従って私の Beatra アカウントに接続してください。
```

## 作例

<p align="center"><img src="assets/cover.webp" width="800" alt="古いアパートから引っ越す歌「Taking the Light With Me」のカバーアート。日の差す空き部屋にテープで閉じた箱が 1 つ。Beatra AI で生成。"></p>

[▶ 試聴する（MP3）](assets/sample.mp3)

*「Taking the Light With Me」の冒頭 60 秒。ラフな歌詞の下書きを Aメロ・Bメロ・サビ・ブリッジに構成した、男性ボーカルのアコースティックフォーク。Beatra AI で生成。*

エージェントへの依頼例：

```text
引っ越しの日に古いアパートを片付ける内容の歌詞の下書きがあります（./lyrics.txt）。Aメロ・Bメロ・サビ・ブリッジに構成し直して、男性ボーカルの温かいアコースティックフォークにして。
```

プロンプト：

```text
Warm acoustic folk song about packing up an old apartment on moving day. Arc: quiet and wistful in the verses, opening into a warm, grateful sing-along chorus, a hushed near-whispered bridge, then a fuller final chorus that settles into a soft ending. Unhurried mid-slow tempo with a gentle swaying feel. Fingerpicked steel-string acoustic guitar, soft upright bass, brushed snare entering at the first chorus, warm upright piano, light cello swell on the choruses. Intimate close-miked male lead, plain-spoken conversational phrasing, soft harmony vocal on the final chorus. Natural room sound, analog warmth, uncluttered mix.
```

## 入力と出力

| | 種類 | 形式 | 仕様 |
| --- | --- | --- | --- |
| **入力** | テキスト：完成した歌詞、下書き、断片的なフレーズ、フック | — | — |
| **出力** | テキスト：ヴァース・コーラス・ブリッジを付けた歌詞とスタイル指定 | — | 編集可能 |
| **出力** | 音声：あなたの歌詞から作った試聴できる曲 | MP3 | — |

## 技術仕様と出力上限

2026-10-18 時点。最新の一覧：https://docs.beatra.ai/ja/docs/models

- **アップロード** — 1 ファイルあたり最大 100 MB。下記の各モデルの入力制限も適用されます
- **テキストから音楽** — 2 モデル（Suno 6、MiniMax Music 3.0）／MP3
  - Suno 6：プロンプトは最大 500、歌詞は最大 5000、タイトルは最大 80 文字
  - MiniMax Music 3.0：プロンプトは最大 2000、歌詞は最大 3500、タイトルは最大 100 文字
- **参照音声から音楽** — 2 モデル（Suno 6、MiniMax Music 3.0）／MP3
  - Suno 6：プロンプトは最大 500、歌詞は最大 5000、タイトルは最大 80 文字／参照音声 6〜480 秒（FLAC、MP3、WAV）
  - MiniMax Music 3.0：プロンプトは最大 300、歌詞は最大 1000、タイトルは最大 100 文字／参照音声 6〜360 秒、最大 50 MB（FLAC、MP3、WAV）

## 得られるもの

- **大切な言葉をそのまま残す** — すべての行を原文どおりに保つか、必ず残すフレーズを指定し、調整モードで残りの歌いやすさを整えます。
- **草稿を曲の構成に整える** — 断片的な素材をヴァース、コーラス、ブリッジ、意味のある反復へ整理し、同じ型を無理に当てはめません。
- **曲の聴こえ方を先に決める** — スタイル、感情、楽器、セクションの対比、歌唱表現を決めてから、試聴できる形にします。

## 活用シーン

- **歌詞は完成しているが曲がない** — 完成した歌詞を保ちながら、明確なセクション、感情の流れ、歌唱の方向を加えます。
- **フレーズや断片だけがある** — 散らばった歌詞行を歌いやすい順序に整理し、意味と印象的なイメージを残します。
- **核になるフックがある** — すでにあるフックを中心に対比と支えるセクションを作り、曲の個性を明確にします。
- **草稿の流れを改善したい** — 必ず残す行を守りながら、リズム、言い回し、韻、反復、セクションのバランスを整えます。

## よくある質問

### どのような歌詞素材から始められますか？

完成した歌詞、書きかけの草稿、断片的な歌詞行、既存のフックから始められます。始めるには、既存の歌詞行またはフックが少なくとも一つ必要です。

### 保持モードでは歌詞をどう扱いますか？

歌詞本文を書いたとおりに使い、文字、句読点、各行とその順番を原文どおりに歌詞シートにします。調整するのは行の前後の改行や空行だけで、セクション名は本文の外に付けます。

### 発音、歌声、曲の長さは指定できますか？

はい。言語、歌い方、歌声の特徴、曲の構成、おおよその長さを伝えれば、その方向で作ります。

### 何が受け取れますか？

ヴァース・コーラス・ブリッジを付けた歌詞とスタイル指定、そしてあなたの歌詞から作った試聴できる MP3 の曲です。

## 更新とセキュリティ

2026 年 10 月のリリース以降、このスキルに自動更新機能はありません。インストールしたファイルだけを実行し、
自動的に置き換えることはありません。更新はインストールに使ったツール（`npx skills update suno-lyrics-to-song` または
`gh skill update suno-lyrics-to-song`）で行ってください。詳細はスキル内の `references/updates-and-security.md` を参照してください。

## ライセンス

このリポジトリのスキルファイル（`SKILL.md`、リファレンス、スクリプト）とこの README は [MIT-0](LICENSE) で提供しています。商用を含め、自由に使用・改変・再配布でき、クレジット表記は不要です。

生成は Beatra のクラウドサービスで行われ、[Beatra 利用規約](https://beatra.ai/terms?utm_source=github&utm_medium=flagship&utm_campaign=lyrics-to-song-skill)が適用されます。

## リンク

- ウェブサイト — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=lyrics-to-song-skill
- ドキュメント — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=lyrics-to-song-skill
- コンソール — https://console.beatra.ai
- AI エージェント向け — https://beatra.ai/llms.txt （インデックス）· https://beatra.ai/llms-full.txt （全スキルを 1 ファイルに）
