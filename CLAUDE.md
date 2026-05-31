# CLAUDE.md — Claude Code への共通指示

このリポジトリは Physical AI 学習のための日本語図解 HTML 解説を生成するためのリポジトリです。

## 対象者プロフィール

- 九州大学 M1（生産環境科学）
- 研究テーマ：RGB-D SLAM + ロボットアーム制御（UR5e + RealSense D435）
- Python 経験あり（ROS2・研究での実装経験）
- 目的：松尾研 Physical AI 基礎編講座（6/25〜）の前提知識補強

## HTML 生成ルール

### スタイル
- 単一 HTML ファイルで完結（CSS・JS を inline に含める）
- Obsidian の iframe で埋め込めること（`<iframe src="xxx.html">` で動作）
- GitHub Pages で公開されることを前提にした相対パス設計
- レスポンシブ対応（スマホ・タブレットでも読める）
- ダークモード対応推奨

### コンテンツ方針
- **日本語**で解説（専門用語は英語併記）
- **「何ができるか」重視**（書き方の細かい説明より概念と用途を優先）
- **図解は SVG で自作**（外部画像不使用）
- 数式はわかりやすく日本語で直感的に説明
- 各セクション末尾に **「研究への接点」** を必ず入れる
  - UR5e・RealSense D435・温室環境・coarse-to-fine プランニングとの関連
- コードは PyTorch の実装例付き（写経できるレベル）

### 構造
- 折りたたみ（`<details>`）を活用してコンパクトに
- 目次を冒頭に配置
- セクションごとにアンカーリンク

### 外部ライブラリ
- cdnjs のみ許可
- highlight.js（コードハイライト）推奨
- MathJax（数式）必要に応じて

## ディレクトリ構造

```
physical-ai-learning/
├── CLAUDE.md                          # このファイル
├── README.md                          # リポジトリ説明
├── template.html                      # HTML雛形
├── _config.yml                        # GitHub Pages 設定
├── pytorch/
│   ├── week1/
│   │   ├── design.md                  # 学習設計書（Claude への指示元）
│   │   └── index.html                 # 生成された解説HTML
│   └── week2/
├── reinforcement-learning/
│   ├── week2-3/
│   └── ...
├── world-model/
└── physical-ai/
    └── lecture-notes/
```

## 学習設計書（design.md）のフォーマット

各週の `design.md` は以下の構造で書く：

```markdown
# [Week X] タイトル

## 学習目標
- 何ができるようになるか

## トピック一覧
1. トピック名 — 概念説明・図解アイデア・研究との接点

## 図解リスト
- 図解1：何を描くか
- 図解2：何を描くか

## コード例
- 実装例の概要

## 参考資料
- 参照した資料
```

## コミットメッセージ規則

```
[week1] PyTorch入門 解説HTML 初版
[week1] 図解修正 - テンソル操作
[rl/week2] 強化学習基礎 解説HTML 追加
```
