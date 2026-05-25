# プロジェクトマネージャー

## 概要
個人事業主向けの単一HTMLファイルのプロジェクト管理ツール。
GitHub Gist でデータを同期する。

## 設計方針
- 単一HTMLファイル（依存なし、Tabler Iconsのみ）
- データは localStorage + GitHub Gist（version 3）
- 既存Gistデータとの後方互換性を必ず維持する

## データ構造
- `projects[]` : プロジェクト（effortRate含む）
- `settings` : { weeklyHours }
- `dailyLogs[]` : { date, projectId, hours }

## 時間管理の設計思想
- エフォート率（%）で各プロジェクトへの時間配分を設定
- 100%が基準、120%はストレッチ目標（頑張った証）
- 毎日夜に30分単位でタップ記録（スマホ想定）
- 週/月の実績 vs 目標を横バーで表示
- ヒートマップで振り返り

## 開発・デプロイ環境
- 開発: WSL + VS Code + Claude Code
- リポジトリ: https://github.com/norihikokimura/project-manager（public）
- 公開URL: https://norihikokimura.github.io/project-manager/
- デプロイ: `git push origin main` → GitHub Pagesが自動反映
- ※ 以前はNetlifyを使用していたが、クレジット制限（300/月）に抵触したためGitHub Pagesに移行済み
