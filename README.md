# 週末弾丸尾道旅行 — Song Project

「週末弾丸尾道旅行」の歌詞・AI楽曲・Cloudflare配信をまとめるプロジェクト。

## 作戦概要

蓋付きのおしゃれなカップに、ウイスキー＋ソーダ。
あたかもコーヒーを嗜む旅人のフリをして、坂と路地と海の街・尾道を自由に歩く。
観光は従。酒飲み散策こそが主。
前回・博多の魂を、広島で再演する。

## 歌詞

- [`lyrics/onomichi-song.md`](lyrics/onomichi-song.md) — 最新版
- [`lyrics/onomichi-song.original.md`](lyrics/onomichi-song.original.md) — 最初のオリジナル(参照用)

コーラス(`[Chorus]` `[Chorus 2]` `[Solo]` `[Chorus 3]`)の連呼「週末弾丸尾道旅行〜」は変更しない前提。
発音をSuno向けに調整し `しゅうまつ　だんがん　おのみち　りょこう〜` (ひらがな・単語区切り)にしている。

`[Verse]`には作戦のカモフラージュを反映した1行を追加:

```
遊んで　はしゃいで　飲もう
コーヒーのフリして　街に溶ける
食ってみな　飛ぶぞ
飲んでみな　飛ぶぞ
```

## Suno での作曲

Sunoへの指示の出し方(サビから始める・発音・早口フロウ・ベース曲のリズム合わせ等)は
[`suno-guide.md`](suno-guide.md) を参照。

## 配信

`public/` 配下がCloudflareへの配信対象。

- `public/index.html` — プレイヤー付きの配信ページ(音源再生+歌詞表示)
- `public/audio/onomichi-song.mp3` — Sunoで生成した音源

`wrangler.jsonc` でWorker名(`syu-matsu-onomichi-song`)と配信対象ディレクトリ(`public`)を固定している。
GitHub連携でこのブランチにpushすると自動デプロイされる。

デプロイURL: `https://syu-matsu-onomichi-song.<アカウント名>.workers.dev`
